# SecDetAssert28

- ea: `0x140040f3c`
- end: `0x140041217`
- name: `SecDetAssert28`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x14002ec70`

## callees

- `0x14000885c`
- `0x140009b80`
- `0x14000ad3c`
- `0x14000add8`
- `0x14000b578`
- `0x14000b824`
- `0x14000b940`
- `0x1400101ac`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x140040f3c`
- `0x140041ca0`
- `0x140041eb8`
- `0x1400425bc`
- `0x1400434bc`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14004106f`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14004106f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041104`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041104`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004117a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004117a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040fbe`
- `ntoskrnl!IoGetCurrentProcess` at `0x140040fbe`

## pseudocode

```c
void __fastcall SecDetAssert28(void *a1, void *a2)
{
  int v2; // r12d
  struct _KPROCESS *CurrentProcess; // rax
  char IsAddressInExecutableSection; // al
  int v7; // r15d
  USHORT v8; // ax
  unsigned int v9; // esi
  int v10; // ebx
  PVOID *v11; // rdi
  __int64 v12; // rsi
  int v13; // r13d
  SIZE_T v14; // rdx
  char *PoolWithTag; // rax
  char *v16; // r14
  int SystemModuleContextByAddress; // ebx
  int CurrentProcessId; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned __int64 v21; // [rsp+50h] [rbp-B0h]
  int v22; // [rsp+58h] [rbp-A8h]
  PSLIST_ENTRY ListEntry; // [rsp+60h] [rbp-A0h] BYREF
  PVOID PcValue; // [rsp+68h] [rbp-98h] BYREF
  PVOID BaseOfImage; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  PVOID BackTrace[20]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 0;
  PcValue = 0;
  ListEntry = 0;
  v26 = 0;
  BaseOfImage = 0;
  v22 = (int)a1;
  if ( *(_BYTE *)DetectionContext )
  {
    if ( (xmmword_14001B740 & 0x40000000) != 0 && !*((_BYTE *)SecData + 1312) )
    {
      CurrentProcess = IoGetCurrentProcess();
      if ( (int)SecGetProcessStartKey(CurrentProcess, &v26) >= 0
        && (*((_QWORD *)DetectionContext + 4) && *((_QWORD *)DetectionContext + 3)
         || (int)SecDetInitializeSystemModuleInfo() >= 0)
        && SecGetThreadStartAddressFromCid(a1, a2, (__int64)&PcValue) >= 0 )
      {
        RtlPcToFileHeader_0(PcValue, &BaseOfImage);
        if ( BaseOfImage )
        {
          IsAddressInExecutableSection = SecIsAddressInExecutableSection(PcValue, BaseOfImage, 256);
          v7 = IsAddressInExecutableSection == 0 ? 2 : 0;
          if ( IsAddressInExecutableSection )
            return;
        }
        else
        {
          v7 = 1;
        }
        v8 = RtlCaptureStackBackTrace(2u, 0x14u, BackTrace, 0);
        v9 = v8;
        v10 = 0;
        if ( v8 )
        {
          while ( 1 )
          {
            v11 = &BackTrace[v10];
            if ( !(unsigned __int8)SecAddressInSystemModuleRegion(*v11, *((_QWORD *)DetectionContext + 3))
              && !(unsigned __int8)SecAddressInSystemModuleRegion(*v11, *((_QWORD *)DetectionContext + 4)) )
            {
              break;
            }
            if ( ++v10 >= v9 )
              return;
          }
          v12 = v9 - v10;
          v13 = 280 * v12;
          v21 = (unsigned __int64)*v11;
          v14 = (unsigned int)(280 * v12);
          if ( qword_140020008 )
            PoolWithTag = (char *)qword_140020008(256, v14, 1682203475);
          else
            PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v14, 0x64446353u);
          v16 = PoolWithTag;
          if ( PoolWithTag )
          {
            memset(PoolWithTag, 0, (unsigned int)(280 * v12));
            _mm_lfence();
            do
            {
              SystemModuleContextByAddress = SecGetSystemModuleContextByAddress(*v11, &ListEntry);
              SecPopulateModuleContextInfo(&v16[280 * v2], *v11, ListEntry);
              if ( SystemModuleContextByAddress >= 0 )
              {
                SecReleaseSystemModuleContext(ListEntry);
                ListEntry = 0;
              }
              ++v11;
              ++v2;
              --v12;
            }
            while ( v12 );
          }
          else
          {
            v13 = 0;
          }
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          v19 = _InterlockedIncrement64((volatile signed __int64 *)SecData + 42);
          v20 = EventWrite28(v19, v7, v22, CurrentProcessId, v26, (__int64)v16, v13, v21, (__int64)PcValue);
          SecIncrementEtwCounters(v20);
          if ( v16 )
            SecFreePool(v16, 0x64446353u);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140040f3c  mov     [rsp-8+arg_10], rbx
0x140040f41  push    rbp
0x140040f42  push    rsi
0x140040f43  push    rdi
0x140040f44  push    r12
0x140040f46  push    r13
0x140040f48  push    r14
0x140040f4a  push    r15
0x140040f4c  lea     rbp, [rsp-30h]
0x140040f51  sub     rsp, 130h
0x140040f58  mov     rax, cs:__security_cookie
0x140040f5f  xor     rax, rsp
0x140040f62  mov     [rbp+60h+var_40], rax
0x140040f66  mov     rax, cs:DetectionContext
0x140040f6d  xor     r12d, r12d
0x140040f70  mov     rbx, rdx
0x140040f73  mov     [rsp+160h+PcValue], r12
0x140040f78  mov     [rsp+160h+ListEntry], r12
0x140040f7d  mov     rdi, rcx
0x140040f80  mov     [rsp+160h+var_E8], r12
0x140040f85  mov     [rsp+160h+BaseOfImage], r12
0x140040f8a  mov     dl, [rax]
0x140040f8c  mov     [rsp+160h+var_108], rcx
0x140040f91  test    dl, dl
0x140040f93  jz      loc_1400411EF
0x140040f99  test    qword ptr cs:xmmword_14001B740, 40000000h
0x140040fa4  jz      loc_1400411EF
0x140040faa  mov     rax, cs:SecData
0x140040fb1  cmp     [rax+520h], r12b
0x140040fb8  jnz     loc_1400411EF
0x140040fbe  call    cs:__imp_IoGetCurrentProcess
0x140040fc5  nop     dword ptr [rax+rax+00h]
0x140040fca  mov     rcx, rax; Process
0x140040fcd  lea     rdx, [rsp+160h+var_E8]
0x140040fd2  call    SecGetProcessStartKey
0x140040fd7  test    eax, eax
0x140040fd9  js      loc_1400411EF
0x140040fdf  mov     rax, cs:DetectionContext
0x140040fe6  cmp     [rax+20h], r12
0x140040fea  jz      short loc_140040FF2
0x140040fec  cmp     [rax+18h], r12
0x140040ff0  jnz     short loc_140040FFF
0x140040ff2  call    SecDetInitializeSystemModuleInfo
0x140040ff7  test    eax, eax
0x140040ff9  js      loc_1400411EF
0x140040fff  lea     r8, [rsp+160h+PcValue]
0x140041004  mov     rdx, rbx
0x140041007  mov     rcx, rdi
0x14004100a  call    SecGetThreadStartAddressFromCid
0x14004100f  test    eax, eax
0x140041011  js      loc_1400411EF
0x140041017  mov     rcx, [rsp+160h+PcValue]; PcValue
0x14004101c  lea     rdx, [rsp+160h+BaseOfImage]; BaseOfImage
0x140041021  call    RtlPcToFileHeader_0
0x140041026  mov     rdx, [rsp+160h+BaseOfImage]
0x14004102b  mov     r14d, 100h
0x140041031  test    rdx, rdx
0x140041034  jz      short loc_14004105B
0x140041036  mov     rcx, [rsp+160h+PcValue]
0x14004103b  mov     r8d, r14d
0x14004103e  call    SecIsAddressInExecutableSection
0x140041043  mov     cl, al
0x140041045  neg     cl
0x140041047  sbb     r15d, r15d
0x14004104a  not     r15d
0x14004104d  and     r15d, 2
0x140041051  test    al, al
0x140041053  jnz     loc_1400411EF
0x140041059  jmp     short loc_140041061
0x14004105b  mov     r15d, 1
0x140041061  xor     r9d, r9d; BackTraceHash
0x140041064  lea     r8, [rbp+60h+BackTrace]; BackTrace
0x140041068  lea     edx, [r9+14h]; FramesToCapture
0x14004106c  lea     ecx, [rdx-12h]; FramesToSkip
0x14004106f  call    cs:__imp_RtlCaptureStackBackTrace
0x140041076  nop     dword ptr [rax+rax+00h]
0x14004107b  movzx   esi, ax
0x14004107e  mov     ebx, r12d
0x140041081  test    esi, esi
0x140041083  jz      loc_1400411EF
0x140041089  mov     rdx, cs:DetectionContext
0x140041090  lea     rdi, [rbp+60h+BackTrace]
0x140041094  mov     eax, ebx
0x140041096  mov     rdx, [rdx+18h]
0x14004109a  lea     rdi, [rdi+rax*8]
0x14004109e  mov     rcx, [rdi]
0x1400410a1  call    SecAddressInSystemModuleRegion
0x1400410a6  test    al, al
0x1400410a8  jnz     short loc_1400410C1
0x1400410aa  mov     rdx, cs:DetectionContext
0x1400410b1  mov     rcx, [rdi]
0x1400410b4  mov     rdx, [rdx+20h]
0x1400410b8  call    SecAddressInSystemModuleRegion
0x1400410bd  test    al, al
0x1400410bf  jz      short loc_1400410CC
0x1400410c1  inc     ebx
0x1400410c3  cmp     ebx, esi
0x1400410c5  jb      short loc_140041089
0x1400410c7  jmp     loc_1400411EF
0x1400410cc  mov     rax, [rdi]
0x1400410cf  sub     esi, ebx
0x1400410d1  imul    r13d, esi, 118h
0x1400410d8  mov     r8d, 64446353h; Tag
0x1400410de  mov     [rsp+160h+var_110], rax
0x1400410e3  mov     rax, cs:qword_140020008
0x1400410ea  mov     ebx, r13d
0x1400410ed  mov     edx, ebx; NumberOfBytes
0x1400410ef  test    rax, rax
0x1400410f2  jz      short loc_1400410FF
0x1400410f4  mov     rcx, r14
0x1400410f7  call    cs:__guard_dispatch_icall_fptr
0x1400410fd  jmp     short loc_140041110
0x1400410ff  mov     ecx, 1; PoolType
0x140041104  call    cs:__imp_ExAllocatePoolWithTag
0x14004110b  nop     dword ptr [rax+rax+00h]
0x140041110  mov     r14, rax
0x140041113  test    rax, rax
0x140041116  jnz     short loc_14004111D
0x140041118  mov     r13d, r12d
0x14004111b  jmp     short loc_14004117A
0x14004111d  mov     r8, rbx; Size
0x140041120  xor     edx, edx; Val
0x140041122  mov     rcx, r14; void *
0x140041125  call    memset
0x14004112a  lfence
0x14004112d  mov     rcx, [rdi]
0x140041130  lea     rdx, [rsp+160h+ListEntry]
0x140041135  call    SecGetSystemModuleContextByAddress
0x14004113a  mov     r8, [rsp+160h+ListEntry]
0x14004113f  mov     ebx, eax
0x140041141  mov     rdx, [rdi]
0x140041144  mov     ecx, r12d
0x140041147  imul    rcx, 118h
0x14004114e  add     rcx, r14
0x140041151  call    SecPopulateModuleContextInfo
0x140041156  test    ebx, ebx
0x140041158  js      short loc_14004116D
0x14004115a  mov     rcx, [rsp+160h+ListEntry]; ListEntry
0x14004115f  call    SecReleaseSystemModuleContext
0x140041164  mov     [rsp+160h+ListEntry], 0
0x14004116d  add     rdi, 8
0x140041171  inc     r12d
0x140041174  sub     rsi, 1
0x140041178  jnz     short loc_14004112D
0x14004117a  call    cs:__imp_PsGetCurrentProcessId
0x140041181  nop     dword ptr [rax+rax+00h]
0x140041186  mov     r8, cs:SecData
0x14004118d  mov     ecx, 1
0x140041192  lock xadd [r8+150h], rcx
0x14004119b  mov     r8, [rsp+160h+PcValue]
0x1400411a0  inc     rcx
0x1400411a3  mov     rdx, [rsp+160h+var_110]
0x1400411a8  mov     r9d, eax
0x1400411ab  mov     [rsp+160h+var_120], r8
0x1400411b0  mov     r8, [rsp+160h+var_E8]
0x1400411b5  mov     [rsp+160h+var_128], rdx
0x1400411ba  mov     edx, r15d
0x1400411bd  mov     [rsp+160h+var_130], r13d
0x1400411c2  mov     [rsp+160h+var_138], r14
0x1400411c7  mov     [rsp+160h+var_140], r8
0x1400411cc  mov     r8d, dword ptr [rsp+160h+var_108]
0x1400411d1  call    EventWrite28
0x1400411d6  mov     ecx, eax
0x1400411d8  call    SecIncrementEtwCounters
0x1400411dd  test    r14, r14
0x1400411e0  jz      short loc_1400411EF
0x1400411e2  mov     edx, 64446353h; Tag
0x1400411e7  mov     rcx, r14; P
0x1400411ea  call    SecFreePool
0x1400411ef  mov     rcx, [rbp+60h+var_40]
0x1400411f3  xor     rcx, rsp; StackCookie
0x1400411f6  call    __security_check_cookie
0x1400411fb  mov     rbx, [rsp+160h+arg_10]
0x140041203  add     rsp, 130h
0x14004120a  pop     r15
0x14004120c  pop     r14
0x14004120e  pop     r13
0x140041210  pop     r12
0x140041212  pop     rdi
0x140041213  pop     rsi
0x140041214  pop     rbp
0x140041215  retn
```
