# SmbCeUpdateServerAvailability

- ea: `0x140094f90`
- end: `0x140095228`
- name: `SmbCeUpdateServerAvailability`
- size: `664`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002d150`
- `0x14003acec`

## callees

- `0x14004c48c`
- `0x14004c538`
- `0x140094f90`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140094ffe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140094ffe`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400950e9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400950e9`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140095078`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140095078`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009520a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009520a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140094fe4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140094fe4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400951fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400951fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400950ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400950ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009505d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009514d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009505d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009514d`

## pseudocode

```c
void __fastcall SmbCeUpdateServerAvailability(__int64 *a1, const UNICODE_STRING *a2, int a3, int a4)
{
  __int64 *v4; // r14
  int v5; // r12d
  __int64 v8; // r13
  __int64 v9; // rsi
  __int64 v10; // rbx
  UNICODE_STRING *v11; // rdi
  __int64 v12; // rax
  UNICODE_STRING *Buffer; // rsi
  wchar_t *v14; // rsi
  UNICODE_STRING *Pool2; // rax
  UNICODE_STRING *v16; // rbx
  int v17; // edx
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rax
  wchar_t *v21; // rcx
  int v22; // r8d
  __int64 v23; // [rsp+A0h] [rbp+8h]

  v4 = a1;
  v5 = a4;
  if ( !a1 )
    v4 = MRxSmbHostUnavailableServers;
  if ( !a4 )
    v5 = 1;
  v8 = MEMORY[0xFFFFF78000000320];
  v9 = 30 * SmbCeTicksPerSecond;
  v23 = 30 * SmbCeTicksPerSecond;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 2), 1u);
  v10 = MEMORY[0xFFFFF78000000320];
  v11 = (UNICODE_STRING *)*v4;
  if ( (__int64 *)*v4 == v4 )
  {
LABEL_13:
    v14 = (wchar_t *)(v8 + v9);
    goto LABEL_14;
  }
  while ( 1 )
  {
    if ( v10 > (__int64)&v11[2].Buffer[300 * SmbCeTicksPerSecond] )
    {
      v12 = *(_QWORD *)&v11->Length;
      if ( *(UNICODE_STRING **)(*(_QWORD *)&v11->Length + 8LL) != v11 )
        goto LABEL_17;
      Buffer = (UNICODE_STRING *)v11->Buffer;
      if ( *(UNICODE_STRING **)&Buffer->Length != v11 )
        goto LABEL_17;
      *(_QWORD *)&Buffer->Length = v12;
      *(_QWORD *)(v12 + 8) = Buffer;
      ExFreePoolWithTag(v11, 0x6D537355u);
      v11 = Buffer;
      goto LABEL_11;
    }
    if ( !RtlCompareUnicodeString(v11 + 1, a2, 1u) )
      break;
LABEL_11:
    v11 = *(UNICODE_STRING **)&v11->Length;
    if ( v11 == (UNICODE_STRING *)v4 )
    {
      v9 = v23;
      goto LABEL_13;
    }
  }
  v14 = (wchar_t *)(v8 + v23);
  if ( v11 )
  {
    if ( a3 >= 0 )
    {
      v20 = *(_QWORD *)&v11->Length;
      if ( *(UNICODE_STRING **)(*(_QWORD *)&v11->Length + 8LL) == v11 )
      {
        v21 = v11->Buffer;
        if ( *(UNICODE_STRING **)v21 == v11 )
        {
          *(_QWORD *)v21 = v20;
          *(_QWORD *)(v20 + 8) = v21;
          ExFreePoolWithTag(v11, 0x6D537355u);
          goto LABEL_31;
        }
      }
LABEL_17:
      __fastfail(3u);
    }
    *(_DWORD *)(&v11[2].MaximumLength + 1) += v5;
    v22 = *(_DWORD *)(&v11[2].MaximumLength + 1);
    v11[2].Buffer = v14;
    *(_DWORD *)&v11[2].Length = a3;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_ZdPD(WPP_GLOBAL_Control->AttachedDevice, 11, v22, (_DWORD)a2, v22, v4[15], a3);
    }
    goto LABEL_31;
  }
LABEL_14:
  if ( a3 < 0 )
  {
    Pool2 = (UNICODE_STRING *)ExAllocatePool2(258, a2->Length + 48LL, 1834185557);
    v16 = Pool2;
    if ( Pool2 )
    {
      Pool2[1].Buffer = &Pool2[3].Length;
      Pool2[1].MaximumLength = a2->Length;
      RtlCopyUnicodeString(Pool2 + 1, a2);
      *(_DWORD *)(&v16[2].MaximumLength + 1) = v5;
      *(_DWORD *)&v16[2].Length = a3;
      v16[2].Buffer = v14;
      v19 = *v4;
      if ( *(__int64 **)(*v4 + 8) != v4 )
        goto LABEL_17;
      *(_QWORD *)&v16->Length = v19;
      v16->Buffer = (wchar_t *)v4;
      *(_QWORD *)(v19 + 8) = v16;
      *v4 = (__int64)v16;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_ZPD(WPP_GLOBAL_Control->AttachedDevice, v17, v18, (_DWORD)a2, v4[15], a3);
      }
    }
  }
LABEL_31:
  ExReleaseResourceLite((PERESOURCE)(v4 + 2));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140094f90  push    rbx
0x140094f92  push    rbp
0x140094f93  push    rsi
0x140094f94  push    rdi
0x140094f95  push    r12
0x140094f97  push    r13
0x140094f99  push    r14
0x140094f9b  push    r15
0x140094f9d  sub     rsp, 58h
0x140094fa1  test    rcx, rcx
0x140094fa4  lea     rax, MRxSmbHostUnavailableServers
0x140094fab  mov     r14, rcx
0x140094fae  mov     r12d, r9d
0x140094fb1  cmovz   r14, rax
0x140094fb5  mov     rbx, 0FFFFF78000000320h
0x140094fbf  test    r9d, r9d
0x140094fc2  mov     eax, 1
0x140094fc7  mov     ebp, r8d
0x140094fca  mov     r15, rdx
0x140094fcd  cmovz   r12d, eax
0x140094fd1  mov     r13, [rbx]
0x140094fd4  imul    rsi, cs:SmbCeTicksPerSecond, 1Eh
0x140094fdc  mov     [rsp+98h+arg_0], rsi
0x140094fe4  call    cs:__imp_KeEnterCriticalRegion
0x140094feb  nop     dword ptr [rax+rax+00h]
0x140094ff0  lea     rax, [r14+10h]
0x140094ff4  mov     dl, 1; Wait
0x140094ff6  mov     rcx, rax; Resource
0x140094ff9  mov     [rsp+98h+Resource], rax
0x140094ffe  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140095005  nop     dword ptr [rax+rax+00h]
0x14009500a  mov     rbx, [rbx]
0x14009500d  mov     rdi, [r14]
0x140095010  cmp     rdi, r14
0x140095013  jz      loc_14009509C
0x140095019  nop     dword ptr [rax+00000000h]
0x140095020  imul    rax, cs:SmbCeTicksPerSecond, 258h
0x14009502b  add     rax, [rdi+28h]
0x14009502f  cmp     rbx, rax
0x140095032  jle     short loc_14009506E
0x140095034  mov     rax, [rdi]
0x140095037  cmp     [rax+8], rdi
0x14009503b  jnz     loc_14009510D
0x140095041  mov     rsi, [rdi+8]
0x140095045  cmp     [rsi], rdi
0x140095048  jnz     loc_14009510D
0x14009504e  mov     [rsi], rax
0x140095051  mov     edx, 6D537355h; Tag
0x140095056  mov     rcx, rdi; P
0x140095059  mov     [rax+8], rsi
0x14009505d  call    cs:__imp_ExFreePoolWithTag
0x140095064  nop     dword ptr [rax+rax+00h]
0x140095069  mov     rdi, rsi
0x14009506c  jmp     short loc_14009508C
0x14009506e  lea     rcx, [rdi+10h]; String1
0x140095072  mov     r8b, 1; CaseInSensitive
0x140095075  mov     rdx, r15; String2
0x140095078  call    cs:__imp_RtlCompareUnicodeString
0x14009507f  nop     dword ptr [rax+rax+00h]
0x140095084  test    eax, eax
0x140095086  jz      loc_140095114
0x14009508c  mov     rdi, [rdi]
0x14009508f  cmp     rdi, r14
0x140095092  jnz     short loc_140095020
0x140095094  mov     rsi, [rsp+98h+arg_0]
0x14009509c  add     rsi, r13
0x14009509f  test    ebp, ebp
0x1400950a1  jns     loc_1400951F9
0x1400950a7  movzx   edx, word ptr [r15]
0x1400950ab  mov     ecx, 102h
0x1400950b0  add     rdx, 30h ; '0'
0x1400950b4  mov     r8d, 6D537355h
0x1400950ba  call    cs:__imp_ExAllocatePool2
0x1400950c1  nop     dword ptr [rax+rax+00h]
0x1400950c6  mov     rbx, rax
0x1400950c9  test    rax, rax
0x1400950cc  jz      loc_1400951F9
0x1400950d2  lea     rcx, [rax+30h]
0x1400950d6  mov     rdx, r15; SourceString
0x1400950d9  mov     [rax+18h], rcx
0x1400950dd  movzx   ecx, word ptr [r15]
0x1400950e1  mov     [rax+12h], cx
0x1400950e5  lea     rcx, [rax+10h]; DestinationString
0x1400950e9  call    cs:__imp_RtlCopyUnicodeString
0x1400950f0  nop     dword ptr [rax+rax+00h]
0x1400950f5  mov     [rbx+24h], r12d
0x1400950f9  mov     [rbx+20h], ebp
0x1400950fc  mov     [rbx+28h], rsi
0x140095100  mov     rax, [r14]
0x140095103  cmp     [rax+8], r14
0x140095107  jz      loc_1400951B2
0x14009510d  mov     ecx, 3
0x140095112  int     29h; Win8: RtlFailFast(ecx)
0x140095114  mov     rsi, [rsp+98h+arg_0]
0x14009511c  add     rsi, r13
0x14009511f  test    rdi, rdi
0x140095122  jz      loc_14009509F
0x140095128  test    ebp, ebp
0x14009512a  js      short loc_14009515E
0x14009512c  mov     rax, [rdi]
0x14009512f  cmp     [rax+8], rdi
0x140095133  jnz     short loc_14009510D
0x140095135  mov     rcx, [rdi+8]
0x140095139  cmp     [rcx], rdi
0x14009513c  jnz     short loc_14009510D
0x14009513e  mov     [rcx], rax
0x140095141  mov     edx, 6D537355h; Tag
0x140095146  mov     [rax+8], rcx
0x14009514a  mov     rcx, rdi; P
0x14009514d  call    cs:__imp_ExFreePoolWithTag
0x140095154  nop     dword ptr [rax+rax+00h]
0x140095159  jmp     loc_1400951F9
0x14009515e  add     [rdi+24h], r12d
0x140095162  mov     r8d, [rdi+24h]
0x140095166  mov     [rdi+28h], rsi
0x14009516a  mov     [rdi+20h], ebp
0x14009516d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140095174  lea     rax, WPP_GLOBAL_Control
0x14009517b  cmp     rcx, rax
0x14009517e  jz      short loc_1400951F9
0x140095180  mov     eax, [rcx+2Ch]
0x140095183  test    al, 1
0x140095185  jz      short loc_1400951F9
0x140095187  cmp     byte ptr [rcx+29h], 1
0x14009518b  jb      short loc_1400951F9
0x14009518d  mov     rax, [r14+78h]
0x140095191  mov     edx, 0Bh
0x140095196  mov     rcx, [rcx+18h]
0x14009519a  mov     r9, r15
0x14009519d  mov     [rsp+98h+var_68], ebp
0x1400951a1  mov     [rsp+98h+var_70], rax
0x1400951a6  mov     dword ptr [rsp+98h+var_78], r8d
0x1400951ab  call    WPP_SF_ZdPD
0x1400951b0  jmp     short loc_1400951F9
0x1400951b2  mov     [rbx], rax
0x1400951b5  mov     [rbx+8], r14
0x1400951b9  mov     [rax+8], rbx
0x1400951bd  mov     [r14], rbx
0x1400951c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400951c7  lea     rax, WPP_GLOBAL_Control
0x1400951ce  cmp     rcx, rax
0x1400951d1  jz      short loc_1400951F9
0x1400951d3  mov     eax, [rcx+2Ch]
0x1400951d6  test    al, 1
0x1400951d8  jz      short loc_1400951F9
0x1400951da  cmp     byte ptr [rcx+29h], 1
0x1400951de  jb      short loc_1400951F9
0x1400951e0  mov     rax, [r14+78h]
0x1400951e4  mov     r9, r15
0x1400951e7  mov     rcx, [rcx+18h]
0x1400951eb  mov     dword ptr [rsp+98h+var_70], ebp
0x1400951ef  mov     [rsp+98h+var_78], rax
0x1400951f4  call    WPP_SF_ZPD
0x1400951f9  mov     rcx, [rsp+98h+Resource]; Resource
0x1400951fe  call    cs:__imp_ExReleaseResourceLite
0x140095205  nop     dword ptr [rax+rax+00h]
0x14009520a  call    cs:__imp_KeLeaveCriticalRegion
0x140095211  nop     dword ptr [rax+rax+00h]
0x140095216  add     rsp, 58h
0x14009521a  pop     r15
0x14009521c  pop     r14
0x14009521e  pop     r13
0x140095220  pop     r12
0x140095222  pop     rdi
0x140095223  pop     rsi
0x140095224  pop     rbp
0x140095225  pop     rbx
0x140095226  retn
```
