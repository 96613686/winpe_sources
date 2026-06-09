# FIPfUserOpenDispatchIOCTL

- ea: `0x140010808`
- end: `0x140010c5f`
- name: `FIPfUserOpenDispatchIOCTL`
- size: `1111`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140012e50`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140003d80`
- `0x14001070c`
- `0x140010808`
- `0x140017700`

## import_xrefs

- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010a80`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010c14`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010a80`
- `ntoskrnl!PsSetCurrentThreadPrefetching` at `0x140010c14`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010911`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010911`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140010b3c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140010b3c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140010931`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140010931`
- `ntoskrnl!NtClose` at `0x140010be2`
- `ntoskrnl!NtClose` at `0x140010be2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010921`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140010921`
- `ntoskrnl!ExGetPreviousMode` at `0x140010956`
- `ntoskrnl!ExGetPreviousMode` at `0x1400109b4`
- `ntoskrnl!ExGetPreviousMode` at `0x140010956`
- `ntoskrnl!ExGetPreviousMode` at `0x1400109b4`
- `ntoskrnl!ExEventObjectType` at `0x140010945`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c00`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001097e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400109dc`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001097e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400109dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400108c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400108c3`
- `ntoskrnl!IoFileObjectType` at `0x14001099f`
- `ntoskrnl!IoFileObjectType` at `0x140010b21`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010a42`
- `ntoskrnl!RtlInitUnicodeString` at `0x140010a42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010c20`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010c20`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010a71`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010a71`

## pseudocode

```c
__int64 __fastcall FIPfUserOpenDispatchIOCTL(__int64 a1)
{
  __int64 v2; // rax
  char *v3; // r14
  char v4; // di
  char v5; // r12
  __int64 v6; // r13
  __int64 v7; // r15
  bool v8; // zf
  NTSTATUS v9; // ebx
  char *Pool2; // rax
  void *v11; // rsi
  KPROCESSOR_MODE PreviousMode; // al
  void *v13; // rsi
  KPROCESSOR_MODE v14; // al
  void *v15; // rcx
  _QWORD *v16; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-89h] BYREF
  _OWORD v19[9]; // [rsp+50h] [rbp-79h] BYREF
  BOOLEAN Prefetching[64]; // [rsp+E0h] [rbp+17h]
  __int64 v22; // [rsp+138h] [rbp+6Fh]
  HANDLE Handle; // [rsp+140h] [rbp+77h] BYREF

  memset(v19, 0, 0x70u);
  Handle = 0;
  *(_QWORD *)Prefetching = 0;
  v2 = *(_QWORD *)(a1 + 184);
  v3 = 0;
  DestinationString = 0;
  v4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(v2 + 48);
  *(_QWORD *)(a1 + 56) = 1080;
  if ( *(_DWORD *)(v2 + 8) == 1080 && *(_DWORD *)(v2 + 16) == 1080 )
  {
    v7 = *(_QWORD *)(a1 + 24);
    v8 = *(_DWORD *)v7 == 2;
    *(_DWORD *)(v7 + 1060) = 0;
    if ( v8 )
    {
      if ( *(_QWORD *)(v6 + 32) )
      {
        v9 = -1073741791;
      }
      else
      {
        v5 = 1;
        Pool2 = (char *)ExAllocatePool2(256, 120, 1869957446);
        v3 = Pool2;
        if ( Pool2 )
        {
          memset(Pool2, 0, 0x78u);
          *((_QWORD *)v3 + 1) = v3;
          *(_QWORD *)v3 = v3;
          *((_QWORD *)v3 + 5) = FIPfUserOpenNotifyConflictStart;
          *((_QWORD *)v3 + 6) = v3;
          *((_QWORD *)v3 + 2) = KeGetCurrentThread();
          *((_QWORD *)v3 + 3) = IoGetCurrentProcess();
          *((_DWORD *)v3 + 9) = (unsigned int)PsGetCurrentThreadId();
          *((_DWORD *)v3 + 8) = (unsigned int)PsGetCurrentProcessId();
          v11 = *(void **)(v7 + 1032);
          PreviousMode = ExGetPreviousMode();
          v9 = ObReferenceObjectByHandle(v11, 3u, (POBJECT_TYPE)ExEventObjectType, PreviousMode, (PVOID *)v3 + 11, 0);
          if ( v9 < 0
            || *(_QWORD *)(v7 + 1040)
            && (v13 = *(void **)(v7 + 1040),
                v14 = ExGetPreviousMode(),
                v9 = ObReferenceObjectByHandle(v13, 0x180u, (POBJECT_TYPE)IoFileObjectType, v14, (PVOID *)v3 + 7, 0),
                v9 < 0) )
          {
            v4 = 0;
          }
          else
          {
            memset(v19, 0, 0x70u);
            DWORD2(v19[4]) = *(_DWORD *)(v7 + 1056);
            *(_QWORD *)&v19[4] = *(_QWORD *)(v7 + 1048);
            *((_QWORD *)&v19[0] + 1) = *((_QWORD *)v3 + 7);
            *(_QWORD *)&v19[0] = v3 + 40;
            *(_WORD *)(v7 + 1026) = 0;
            RtlInitUnicodeString(&DestinationString, (PCWSTR)(v7 + 4));
            LODWORD(v19[1]) = 48;
            *(_QWORD *)&v19[2] = &DestinationString;
            v19[3] = 0;
            *((_QWORD *)&v19[1] + 1) = 0;
            DWORD2(v19[2]) = 64;
            KeEnterCriticalRegion();
            Prefetching[0] = PsSetCurrentThreadPrefetching(1u);
            v4 = 1;
            HIDWORD(v22) = _InterlockedIncrement(&dword_140009640);
            LODWORD(v22) = ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
                         + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24);
            *(_QWORD *)(v3 + 100) = v22;
            v9 = FIPfInterfaceOpen(v19);
            *(_DWORD *)(v7 + 1060) = DWORD2(v19[6]);
            if ( v9 >= 0 )
            {
              *((_QWORD *)v3 + 8) = *(_QWORD *)&v19[5];
              v15 = (void *)*((_QWORD *)&v19[5] + 1);
              *((_QWORD *)v3 + 9) = *((_QWORD *)&v19[5] + 1);
              *((_QWORD *)v3 + 10) = *(_QWORD *)&v19[6];
              v9 = ObOpenObjectByPointer(v15, 0x40u, 0, v19[4], (POBJECT_TYPE)IoFileObjectType, 1, &Handle);
              if ( v9 >= 0 )
              {
                FILockExclusiveAcquire(&qword_140009760);
                if ( *(_QWORD *)(v6 + 32) )
                {
                  v9 = -1073741791;
                }
                else
                {
                  v16 = (_QWORD *)qword_140009770;
                  if ( *(__int64 **)qword_140009770 != &qword_140009768 )
                    __fastfail(3u);
                  *(_QWORD *)v3 = &qword_140009768;
                  v9 = 0;
                  *((_QWORD *)v3 + 1) = v16;
                  *v16 = v3;
                  ++dword_140009778;
                  qword_140009770 = (__int64)v3;
                  *(_QWORD *)(v6 + 32) = v3;
                  *((_QWORD *)v3 + 14) = v6;
                  v3 = 0;
                }
                FILockExclusiveRelease(&qword_140009760);
                if ( !v9 )
                {
                  *(_QWORD *)(v7 + 1072) = Handle;
                  Handle = 0;
                  goto LABEL_25;
                }
              }
            }
          }
        }
        else
        {
          v9 = -1073741670;
        }
      }
    }
    else
    {
      v9 = -1073740971;
    }
  }
  else
  {
    v7 = 0;
    v9 = -1073741306;
  }
  if ( Handle )
    NtClose(Handle);
LABEL_25:
  if ( v3 )
  {
    FIPfUserOpenCleanup(v3);
    ExFreePoolWithTag(v3, 0);
  }
  if ( v4 )
  {
    PsSetCurrentThreadPrefetching(Prefetching[0]);
    KeLeaveCriticalRegion();
  }
  if ( v5 )
  {
    *(_DWORD *)(v7 + 1064) = v9;
    v9 = 0;
  }
  *(_DWORD *)(a1 + 48) = v9;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140010808  mov     [rsp-8+arg_18], rbx
0x14001080d  mov     [rsp-8+arg_0], rcx
0x140010812  push    rbp
0x140010813  push    rsi
0x140010814  push    rdi
0x140010815  push    r12
0x140010817  push    r13
0x140010819  push    r14
0x14001081b  push    r15
0x14001081d  lea     rbp, [rsp-27h]
0x140010822  sub     rsp, 0F0h
0x140010829  xor     edx, edx; Val
0x14001082b  mov     rbx, rcx
0x14001082e  lea     rcx, [rbp+57h+var_D0]; void *
0x140010832  lea     r8d, [rdx+70h]; Size
0x140010836  call    memset
0x14001083b  xor     esi, esi
0x14001083d  xor     eax, eax
0x14001083f  mov     [rbp+57h+arg_10], rsi
0x140010843  mov     ecx, 438h
0x140010848  mov     qword ptr [rbp+57h+Prefetching], rax
0x14001084c  xorps   xmm0, xmm0
0x14001084f  mov     rax, [rbx+0B8h]
0x140010856  mov     r14d, esi
0x140010859  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x14001085e  mov     dil, sil
0x140010861  mov     byte ptr [rbp+57h+arg_8], sil
0x140010865  mov     r12b, sil
0x140010868  mov     r13, [rax+30h]
0x14001086c  mov     [rbx+38h], rcx
0x140010870  cmp     [rax+8], ecx
0x140010873  jnz     loc_140010BD1
0x140010879  cmp     [rax+10h], ecx
0x14001087c  jnz     loc_140010BD1
0x140010882  mov     r15, [rbx+18h]
0x140010886  cmp     dword ptr [r15], 2
0x14001088a  mov     [r15+424h], esi
0x140010891  jz      short loc_14001089D
0x140010893  mov     ebx, 0C0000355h
0x140010898  jmp     loc_140010BD9
0x14001089d  cmp     [r13+20h], rsi
0x1400108a1  jz      short loc_1400108AD
0x1400108a3  mov     ebx, 0C0000021h
0x1400108a8  jmp     loc_140010BD9
0x1400108ad  mov     ebx, 78h ; 'x'
0x1400108b2  mov     r8d, 6F754946h
0x1400108b8  mov     edx, ebx
0x1400108ba  mov     ecx, 100h
0x1400108bf  lea     r12d, [rbx-77h]
0x1400108c3  call    cs:__imp_ExAllocatePool2
0x1400108ca  nop     dword ptr [rax+rax+00h]
0x1400108cf  mov     r14, rax
0x1400108d2  test    rax, rax
0x1400108d5  jnz     short loc_1400108E1
0x1400108d7  mov     ebx, 0C000009Ah
0x1400108dc  jmp     loc_140010BD9
0x1400108e1  mov     r8, rbx; Size
0x1400108e4  xor     edx, edx; Val
0x1400108e6  mov     rcx, r14; void *
0x1400108e9  call    memset
0x1400108ee  mov     [r14+8], r14
0x1400108f2  lea     rax, FIPfUserOpenNotifyConflictStart
0x1400108f9  mov     [r14], r14
0x1400108fc  mov     [r14+28h], rax
0x140010900  mov     [r14+30h], r14
0x140010904  mov     rax, gs:188h
0x14001090d  mov     [r14+10h], rax
0x140010911  call    cs:__imp_IoGetCurrentProcess
0x140010918  nop     dword ptr [rax+rax+00h]
0x14001091d  mov     [r14+18h], rax
0x140010921  call    cs:__imp_PsGetCurrentThreadId
0x140010928  nop     dword ptr [rax+rax+00h]
0x14001092d  mov     [r14+24h], eax
0x140010931  call    cs:__imp_PsGetCurrentProcessId
0x140010938  nop     dword ptr [rax+rax+00h]
0x14001093d  mov     [r14+20h], eax
0x140010941  lea     rbx, [r14+58h]
0x140010945  mov     rax, cs:ExEventObjectType
0x14001094c  mov     rsi, [r15+408h]
0x140010953  mov     rdi, [rax]
0x140010956  call    cs:__imp_ExGetPreviousMode
0x14001095d  nop     dword ptr [rax+rax+00h]
0x140010962  mov     [rsp+120h+HandleInformation], 0; HandleInformation
0x14001096b  mov     r8, rdi; ObjectType
0x14001096e  mov     r9b, al; AccessMode
0x140010971  mov     [rsp+120h+Object], rbx; Object
0x140010976  mov     edx, 3; DesiredAccess
0x14001097b  mov     rcx, rsi; Handle
0x14001097e  call    cs:__imp_ObReferenceObjectByHandle
0x140010985  nop     dword ptr [rax+rax+00h]
0x14001098a  xor     esi, esi
0x14001098c  mov     ebx, eax
0x14001098e  test    eax, eax
0x140010990  js      loc_140010BCB
0x140010996  cmp     [r15+410h], rsi
0x14001099d  jz      short loc_1400109F4
0x14001099f  mov     rax, cs:__imp_IoFileObjectType
0x1400109a6  lea     rbx, [r14+38h]
0x1400109aa  mov     rsi, [r15+410h]
0x1400109b1  mov     rdi, [rax]
0x1400109b4  call    cs:__imp_ExGetPreviousMode
0x1400109bb  nop     dword ptr [rax+rax+00h]
0x1400109c0  mov     [rsp+120h+HandleInformation], 0; HandleInformation
0x1400109c9  mov     r8, rdi; ObjectType
0x1400109cc  mov     r9b, al; AccessMode
0x1400109cf  mov     [rsp+120h+Object], rbx; Object
0x1400109d4  mov     edx, 180h; DesiredAccess
0x1400109d9  mov     rcx, rsi; Handle
0x1400109dc  call    cs:__imp_ObReferenceObjectByHandle
0x1400109e3  nop     dword ptr [rax+rax+00h]
0x1400109e8  xor     esi, esi
0x1400109ea  mov     ebx, eax
0x1400109ec  test    eax, eax
0x1400109ee  js      loc_140010BCB
0x1400109f4  xor     edx, edx; Val
0x1400109f6  lea     rcx, [rbp+57h+var_D0]; void *
0x1400109fa  lea     r8d, [rdx+70h]; Size
0x1400109fe  call    memset
0x140010a03  mov     eax, [r15+420h]
0x140010a0a  lea     rdx, [r15+4]; SourceString
0x140010a0e  mov     [rbp+57h+var_88], eax
0x140010a11  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x140010a16  mov     eax, [r15+418h]
0x140010a1d  mov     [rbp+57h+DesiredAccess], eax
0x140010a20  mov     eax, [r15+41Ch]
0x140010a27  mov     [rbp+57h+var_8C], eax
0x140010a2a  mov     rax, [r14+38h]
0x140010a2e  mov     [rbp+57h+var_C8], rax
0x140010a32  lea     rax, [r14+28h]
0x140010a36  mov     [rbp+57h+var_D0], rax
0x140010a3a  mov     [r15+402h], si
0x140010a42  call    cs:__imp_RtlInitUnicodeString
0x140010a49  nop     dword ptr [rax+rax+00h]
0x140010a4e  lea     rax, [rsp+120h+DestinationString]
0x140010a53  mov     [rbp+57h+var_C0], 30h ; '0'
0x140010a5a  xorps   xmm0, xmm0
0x140010a5d  mov     [rbp+57h+var_B0], rax
0x140010a61  movdqa  [rbp+57h+var_A0], xmm0
0x140010a66  mov     [rbp+57h+var_B8], rsi
0x140010a6a  mov     [rbp+57h+var_A8], 40h ; '@'
0x140010a71  call    cs:__imp_KeEnterCriticalRegion
0x140010a78  nop     dword ptr [rax+rax+00h]
0x140010a7d  mov     cl, r12b; Prefetching
0x140010a80  call    cs:__imp_PsSetCurrentThreadPrefetching
0x140010a87  nop     dword ptr [rax+rax+00h]
0x140010a8c  mov     [rbp+57h+Prefetching], al
0x140010a8f  mov     dil, r12b
0x140010a92  mov     eax, r12d
0x140010a95  lock xadd cs:dword_140009640, eax
0x140010a9d  add     eax, r12d
0x140010aa0  mov     rcx, 0FFFFF78000000320h
0x140010aaa  mov     dword ptr [rbp+57h+arg_8+4], eax
0x140010aad  mov     rcx, [rcx]
0x140010ab0  mov     eax, ds:0FFFFF78000000004h
0x140010ab9  mov     edx, ecx
0x140010abb  mov     r8d, eax
0x140010abe  shr     rcx, 20h
0x140010ac2  imul    ecx, eax
0x140010ac5  imul    r8, rdx
0x140010ac9  shl     ecx, 8
0x140010acc  shr     r8, 18h
0x140010ad0  add     r8d, ecx
0x140010ad3  lea     rcx, [rbp+57h+var_D0]
0x140010ad7  mov     dword ptr [rbp+57h+arg_8], r8d
0x140010adb  mov     rax, [rbp+57h+arg_8]
0x140010adf  mov     [r14+64h], rax
0x140010ae3  call    FIPfInterfaceOpen
0x140010ae8  mov     ebx, eax
0x140010aea  mov     eax, [rbp+57h+var_68]
0x140010aed  mov     [r15+424h], eax
0x140010af4  test    ebx, ebx
0x140010af6  js      loc_140010BD9
0x140010afc  mov     rax, [rbp+57h+var_80]
0x140010b00  mov     [r14+40h], rax
0x140010b04  mov     rcx, [rbp+57h+var_78]; Object
0x140010b08  mov     [r14+48h], rcx
0x140010b0c  mov     rax, [rbp+57h+var_70]
0x140010b10  mov     [r14+50h], rax
0x140010b14  lea     rax, [rbp+57h+arg_10]
0x140010b18  mov     r9d, [rbp+57h+DesiredAccess]; DesiredAccess
0x140010b1c  mov     [rsp+120h+Handle], rax; Handle
0x140010b21  mov     rax, cs:__imp_IoFileObjectType
0x140010b28  mov     byte ptr [rsp+120h+HandleInformation], r12b; AccessMode
0x140010b2d  mov     r8, [rax]
0x140010b30  mov     [rsp+120h+Object], r8; ObjectType
0x140010b35  xor     r8d, r8d; PassedAccessState
0x140010b38  lea     edx, [r8+40h]; HandleAttributes
0x140010b3c  call    cs:__imp_ObOpenObjectByPointer
0x140010b43  nop     dword ptr [rax+rax+00h]
0x140010b48  mov     ebx, eax
0x140010b4a  test    eax, eax
0x140010b4c  js      loc_140010BD9
0x140010b52  lea     rcx, qword_140009760
0x140010b59  call    FILockExclusiveAcquire
0x140010b5e  cmp     [r13+20h], rsi
0x140010b62  jnz     short loc_140010BA5
0x140010b64  mov     rax, cs:qword_140009770
0x140010b6b  lea     rdx, qword_140009768
0x140010b72  cmp     [rax], rdx
0x140010b75  jz      short loc_140010B7E
0x140010b77  mov     ecx, 3
0x140010b7c  int     29h; Win8: RtlFailFast(ecx)
0x140010b7e  mov     [r14], rdx
0x140010b81  mov     ebx, esi
0x140010b83  mov     [r14+8], rax
0x140010b87  mov     [rax], r14
0x140010b8a  add     cs:dword_140009778, r12d
0x140010b91  mov     cs:qword_140009770, r14
0x140010b98  mov     [r13+20h], r14
0x140010b9c  mov     [r14+70h], r13
0x140010ba0  mov     r14, rsi
0x140010ba3  jmp     short loc_140010BAA
0x140010ba5  mov     ebx, 0C0000021h
0x140010baa  lea     rcx, qword_140009760
0x140010bb1  call    FILockExclusiveRelease
0x140010bb6  test    ebx, ebx
0x140010bb8  jnz     short loc_140010BD9
0x140010bba  mov     rax, [rbp+57h+arg_10]
0x140010bbe  mov     [r15+430h], rax
0x140010bc5  mov     [rbp+57h+arg_10], rsi
0x140010bc9  jmp     short loc_140010BEE
0x140010bcb  mov     dil, byte ptr [rbp+57h+arg_8]
0x140010bcf  jmp     short loc_140010BD9
0x140010bd1  mov     r15, rsi
0x140010bd4  mov     ebx, 0C0000206h
0x140010bd9  mov     rcx, [rbp+57h+arg_10]; Handle
0x140010bdd  test    rcx, rcx
0x140010be0  jz      short loc_140010BEE
0x140010be2  call    cs:__imp_NtClose
0x140010be9  nop     dword ptr [rax+rax+00h]
0x140010bee  test    r14, r14
0x140010bf1  jz      short loc_140010C0C
0x140010bf3  mov     rcx, r14
0x140010bf6  call    FIPfUserOpenCleanup
0x140010bfb  xor     edx, edx; Tag
0x140010bfd  mov     rcx, r14; P
0x140010c00  call    cs:__imp_ExFreePoolWithTag
0x140010c07  nop     dword ptr [rax+rax+00h]
0x140010c0c  test    dil, dil
0x140010c0f  jz      short loc_140010C2C
0x140010c11  mov     cl, [rbp+57h+Prefetching]; Prefetching
0x140010c14  call    cs:__imp_PsSetCurrentThreadPrefetching
0x140010c1b  nop     dword ptr [rax+rax+00h]
0x140010c20  call    cs:__imp_KeLeaveCriticalRegion
0x140010c27  nop     dword ptr [rax+rax+00h]
0x140010c2c  test    r12b, r12b
0x140010c2f  jz      short loc_140010C3A
0x140010c31  mov     [r15+428h], ebx
0x140010c38  mov     ebx, esi
0x140010c3a  mov     rax, [rbp+57h+arg_0]
0x140010c3e  mov     [rax+30h], ebx
0x140010c41  mov     eax, ebx
0x140010c43  mov     rbx, [rsp+120h+arg_18]
0x140010c4b  add     rsp, 0F0h
0x140010c52  pop     r15
0x140010c54  pop     r14
0x140010c56  pop     r13
0x140010c58  pop     r12
0x140010c5a  pop     rdi
0x140010c5b  pop     rsi
0x140010c5c  pop     rbp
0x140010c5d  retn
```
