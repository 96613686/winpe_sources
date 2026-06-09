# IASSamOpenUser

- ea: `0x18002addc`
- end: `0x18002afac`
- name: `IASSamOpenUser`
- size: `464`
- prototype: `__int64 __usercall@<rax>(wchar_t *Source@<rcx>, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180027b58`
- `0x180027be8`
- `0x1800282e4`
- `0x180029a28`
- `0x18002a248`

## callees

- `0x180001f26`
- `0x18002aa10`
- `0x18002ab84`
- `0x18002addc`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002aeb6`
- `ntdll!RtlLengthSid` at `0x18002aeb6`
- `ntdll!RtlAllocateHeap` at `0x18002aed0`
- `ntdll!RtlAllocateHeap` at `0x18002aed0`
- `SAMLIB!SamFreeMemory` at `0x18002af38`
- `SAMLIB!SamFreeMemory` at `0x18002af38`
- `SAMLIB!SamCloseHandle` at `0x18002af01`
- `SAMLIB!SamCloseHandle` at `0x18002af6b`
- `SAMLIB!SamCloseHandle` at `0x18002af01`
- `SAMLIB!SamCloseHandle` at `0x18002af6b`

## pseudocode

```c
__int64 __fastcall IASSamOpenUser(wchar_t *Source, int a2, int a3, int a4, __int64 a5, _QWORD *a6, _QWORD *a7)
{
  int v7; // esi
  wchar_t *v8; // rdx
  unsigned int v9; // r15d
  int v10; // edi
  int v11; // r10d
  BOOL v13; // ecx
  ULONG v14; // ebx
  ULONG v15; // eax
  PSID v16; // rdi
  ULONG v17; // ebp
  PVOID Heap; // rax
  PVOID v19; // rsi
  PSID Sid; // [rsp+40h] [rbp-58h] BYREF
  __int64 v22[10]; // [rsp+48h] [rbp-50h] BYREF
  BOOL v25; // [rsp+B0h] [rbp+18h]

  v7 = a2;
  v8 = Source;
  Sid = 0;
  v22[0] = 0;
  v9 = 0;
  v10 = 0;
  v11 = a4;
  v13 = (a3 | 0x40) == a3;
  v25 = v13;
  while ( 1 )
  {
    v14 = IASSamOpenDomain(v8, (__int64)v8, v11, v9 != 0, v13, &Sid, v22);
    if ( !v14 )
      break;
LABEL_24:
    v13 = v25;
    ++v9;
    v11 = a4;
    v8 = Source;
    if ( v9 >= 2 )
      return v14;
  }
  v15 = IASSamLookupUser(v22[0], v7, a3, a5, (__int64)a7);
  v14 = v15;
  if ( v15 )
  {
    if ( v15 != 1332 )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( a6 )
  {
    v16 = Sid;
    if ( Sid )
    {
      v17 = RtlLengthSid(Sid);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
      v19 = Heap;
      if ( Heap )
      {
        memcpy_0(Heap, v16, v17);
        *a6 = v19;
        goto LABEL_13;
      }
      *a6 = 0;
    }
    else
    {
      *a6 = 0;
    }
    SamCloseHandle(*a7);
    *a7 = 0;
    v14 = -1073741801;
  }
LABEL_13:
  v7 = a2;
  v10 = 1;
LABEL_14:
  if ( Sid != theAccountDomainSid && Sid != (PSID)qword_1800404D0 )
    SamFreeMemory(Sid);
  if ( v22[0] == qword_1800404D8 )
  {
    if ( !v10 )
      Destination = 0;
    _InterlockedDecrement(&dword_1800404E0);
  }
  else if ( v22[0] != theAccountDomainHandle )
  {
    SamCloseHandle(v22[0]);
  }
  if ( !v10 )
    goto LABEL_24;
  return v14;
}

```

## disassembly

```asm
0x18002addc  mov     rax, rsp
0x18002addf  mov     [rax+20h], r9d
0x18002ade3  mov     [rax+10h], rdx
0x18002ade7  mov     [rax+8], rcx
0x18002adeb  push    rbx
0x18002adec  push    rbp
0x18002aded  push    rsi
0x18002adee  push    rdi
0x18002adef  push    r12
0x18002adf1  push    r13
0x18002adf3  push    r14
0x18002adf5  push    r15
0x18002adf7  sub     rsp, 58h
0x18002adfb  mov     r14, [rsp+98h+arg_28]
0x18002ae03  mov     rsi, rdx
0x18002ae06  mov     r12, [rsp+98h+arg_30]
0x18002ae0e  mov     rdx, rcx
0x18002ae11  xor     ecx, ecx
0x18002ae13  mov     qword ptr [rax-58h], 0
0x18002ae1b  mov     qword ptr [rax-50h], 0
0x18002ae23  xor     r15d, r15d
0x18002ae26  mov     eax, r8d
0x18002ae29  xor     edi, edi
0x18002ae2b  or      eax, 40h
0x18002ae2e  mov     r10d, r9d
0x18002ae31  cmp     eax, r8d
0x18002ae34  mov     r13d, r8d
0x18002ae37  setz    cl
0x18002ae3a  mov     [rsp+98h+arg_10], ecx
0x18002ae41  xor     r9d, r9d
0x18002ae44  lea     rax, [rsp+98h+var_50]
0x18002ae49  mov     [rsp+98h+var_68], rax; __int64
0x18002ae4e  test    r15d, r15d
0x18002ae51  lea     rax, [rsp+98h+Sid]
0x18002ae56  mov     r8d, r10d
0x18002ae59  mov     [rsp+98h+var_70], rax; __int64
0x18002ae5e  setnz   r9b
0x18002ae62  mov     [rsp+98h+var_78], ecx; int
0x18002ae66  mov     rcx, rdx; Source
0x18002ae69  call    IASSamOpenDomain
0x18002ae6e  mov     ebx, eax
0x18002ae70  test    eax, eax
0x18002ae72  jnz     loc_18002AF75
0x18002ae78  mov     r9, [rsp+98h+arg_20]
0x18002ae80  mov     r8d, r13d
0x18002ae83  mov     rcx, [rsp+98h+var_50]
0x18002ae88  mov     rdx, rsi
0x18002ae8b  mov     qword ptr [rsp+98h+var_78], r12
0x18002ae90  call    IASSamLookupUser
0x18002ae95  mov     ebx, eax
0x18002ae97  test    eax, eax
0x18002ae99  jz      short loc_18002AEA4
0x18002ae9b  cmp     eax, 534h
0x18002aea0  jz      short loc_18002AF14
0x18002aea2  jmp     short loc_18002AF21
0x18002aea4  test    r14, r14
0x18002aea7  jz      short loc_18002AF14
0x18002aea9  mov     rdi, [rsp+98h+Sid]
0x18002aeae  test    rdi, rdi
0x18002aeb1  jz      short loc_18002AEF6
0x18002aeb3  mov     rcx, rdi; Sid
0x18002aeb6  call    cs:__imp_RtlLengthSid
0x18002aebc  mov     rcx, gs:60h
0x18002aec5  xor     edx, edx; Flags
0x18002aec7  mov     r8d, eax; Size
0x18002aeca  mov     ebp, eax
0x18002aecc  mov     rcx, [rcx+30h]; HeapHandle
0x18002aed0  call    cs:__imp_RtlAllocateHeap
0x18002aed6  mov     rsi, rax
0x18002aed9  test    rax, rax
0x18002aedc  jz      short loc_18002AEF1
0x18002aede  mov     r8d, ebp; Size
0x18002aee1  mov     rdx, rdi; Src
0x18002aee4  mov     rcx, rax; void *
0x18002aee7  call    memcpy_0
0x18002aeec  mov     [r14], rsi
0x18002aeef  jmp     short loc_18002AF14
0x18002aef1  mov     [r14], rsi
0x18002aef4  jmp     short loc_18002AEFD
0x18002aef6  mov     qword ptr [r14], 0
0x18002aefd  mov     rcx, [r12]
0x18002af01  call    cs:__imp_SamCloseHandle
0x18002af07  mov     qword ptr [r12], 0
0x18002af0f  mov     ebx, 0C0000017h
0x18002af14  mov     rsi, [rsp+98h+arg_8]
0x18002af1c  mov     edi, 1
0x18002af21  mov     rcx, [rsp+98h+Sid]
0x18002af26  cmp     rcx, cs:theAccountDomainSid
0x18002af2d  jz      short loc_18002AF3E
0x18002af2f  cmp     rcx, cs:qword_1800404D0
0x18002af36  jz      short loc_18002AF3E
0x18002af38  call    cs:__imp_SamFreeMemory
0x18002af3e  mov     rcx, [rsp+98h+var_50]
0x18002af43  cmp     rcx, cs:qword_1800404D8
0x18002af4a  jnz     short loc_18002AF62
0x18002af4c  test    edi, edi
0x18002af4e  jnz     short loc_18002AF59
0x18002af50  xor     eax, eax
0x18002af52  mov     cs:Destination, ax
0x18002af59  lock dec cs:dword_1800404E0
0x18002af60  jmp     short loc_18002AF71
0x18002af62  cmp     rcx, cs:theAccountDomainHandle
0x18002af69  jz      short loc_18002AF71
0x18002af6b  call    cs:__imp_SamCloseHandle
0x18002af71  test    edi, edi
0x18002af73  jnz     short loc_18002AF99
0x18002af75  mov     ecx, [rsp+98h+arg_10]
0x18002af7c  inc     r15d
0x18002af7f  mov     r10d, [rsp+98h+arg_18]
0x18002af87  mov     rdx, [rsp+98h+arg_0]
0x18002af8f  cmp     r15d, 2
0x18002af93  jb      loc_18002AE41
0x18002af99  mov     eax, ebx
0x18002af9b  add     rsp, 58h
0x18002af9f  pop     r15
0x18002afa1  pop     r14
0x18002afa3  pop     r13
0x18002afa5  pop     r12
0x18002afa7  pop     rdi
0x18002afa8  pop     rsi
0x18002afa9  pop     rbp
0x18002afaa  pop     rbx
0x18002afab  retn
```
