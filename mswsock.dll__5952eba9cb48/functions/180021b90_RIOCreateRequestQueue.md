# RIOCreateRequestQueue

- ea: `0x180021b90`
- end: `0x180021e45`
- name: `RIOCreateRequestQueue`
- size: `693`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180008190`
- `0x180008250`
- `0x180021b90`
- `0x1800222f0`
- `0x180022bd2`
- `0x18002804c`
- `0x18002819c`
- `0x180028990`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180021ddb`
- `ntdll!RtlFreeHeap` at `0x180021df3`
- `ntdll!RtlFreeHeap` at `0x180021ddb`
- `ntdll!RtlFreeHeap` at `0x180021df3`
- `ntdll!NtDeviceIoControlFile` at `0x180021d42`
- `ntdll!NtDeviceIoControlFile` at `0x180021d42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021da9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021da9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021c6f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021d9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021e0f`

## pseudocode

```c
__int64 __fastcall RIOCreateRequestQueue(
        HANDLE FileHandle,
        int a2,
        int a3,
        int a4,
        int a5,
        _DWORD *a6,
        _DWORD *a7,
        __int64 a8)
{
  __int64 v12; // rax
  __int64 v13; // rdi
  DWORD v14; // ecx
  struct _RTL_CRITICAL_SECTION *v15; // r13
  __int64 v16; // r15
  __int64 v17; // r8
  unsigned int v18; // esi
  unsigned int v19; // r14d
  __int64 RequestQueue; // rax
  __int64 v21; // rbx
  DWORD v22; // ecx
  HANDLE RegDomain; // rax
  NTSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  _DWORD InputBuffer[6]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v30; // [rsp+88h] [rbp-31h]
  unsigned int v31; // [rsp+90h] [rbp-29h]
  int v32; // [rsp+94h] [rbp-25h]
  __int64 v33; // [rsp+98h] [rbp-21h]
  HANDLE v34; // [rsp+A0h] [rbp-19h]
  __int64 v35; // [rsp+A8h] [rbp-11h]

  IoStatusBlock = 0;
  memset_0(InputBuffer, 0, 0x40u);
  if ( !a6 || !a7 || !a2 && !a4 || a3 != 1 || a5 != 1 )
  {
    v14 = 10022;
    goto LABEL_35;
  }
  InputBuffer[2] = a6[2];
  InputBuffer[1] = a7[2];
  InputBuffer[0] = 3;
  if ( *a6 != -1582119980 || *a7 != -1582119980 )
    goto LABEL_33;
  v12 = SockFindAndReferenceSocket(FileHandle);
  v13 = v12;
  if ( !v12 )
  {
    v14 = 10038;
LABEL_35:
    SetLastError(v14);
    return 0;
  }
  v15 = (struct _RTL_CRITICAL_SECTION *)(v12 + 224);
  v16 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 224));
  if ( *(_DWORD *)(v13 + 24) == 4 || *(_DWORD *)(v13 + 24) == -1 )
  {
    v21 = 0;
    goto LABEL_26;
  }
  v18 = a2 + 1;
  v19 = a4 + 1;
  LOBYTE(v17) = *(_DWORD *)(v13 + 32) == 1;
  RequestQueue = AllocateRequestQueue(v18, v19, v17, 0);
  v21 = RequestQueue;
  if ( !RequestQueue )
  {
LABEL_14:
    v22 = 10055;
LABEL_27:
    SetLastError(v22);
    goto LABEL_28;
  }
  v31 = v18;
  InputBuffer[3] = v19;
  v32 = 72 * v18 + 16;
  InputBuffer[4] = 72 * v19 + 16;
  v30 = *(_QWORD *)(RequestQueue + 32);
  v33 = *(_QWORD *)(RequestQueue + 40);
  v35 = a8;
  RegDomain = MswRioRegDomain;
  if ( MswRioRegDomain == (HANDLE)-1LL )
    RegDomain = CreateRegDomain();
  v34 = RegDomain;
  v24 = NtDeviceIoControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1211Bu, InputBuffer, 0x40u, 0, 0);
  if ( v24 == 259 )
LABEL_33:
    RioException();
  if ( v24 < 0 )
  {
    if ( v24 == -1073741618 )
      goto LABEL_14;
    if ( v24 == -1073741808 )
    {
      v22 = 10045;
      goto LABEL_27;
    }
    if ( v24 != -1073741811 )
    {
      v22 = 10014;
      goto LABEL_27;
    }
LABEL_26:
    v22 = 10022;
    goto LABEL_27;
  }
  *(_QWORD *)(v13 + 16) = v21;
  v16 = v21;
  *(_QWORD *)(v21 + 8) = FileHandle;
  v21 = 0;
LABEL_28:
  LeaveCriticalSection(v15);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1 )
    SockDestroySocket(v13, v25, v26);
  if ( v21 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, *(PVOID *)(v21 + 32));
    RtlFreeHeap(SockPrivateHeap, 0, (PVOID)v21);
  }
  return v16;
}

```

## disassembly

```asm
0x180021b90  mov     [rsp-8+arg_10], rbx
0x180021b95  push    rbp
0x180021b96  push    rsi
0x180021b97  push    rdi
0x180021b98  push    r12
0x180021b9a  push    r13
0x180021b9c  push    r14
0x180021b9e  push    r15
0x180021ba0  lea     rbp, [rsp-7]
0x180021ba5  sub     rsp, 0C0h
0x180021bac  mov     rax, cs:__security_cookie
0x180021bb3  xor     rax, rsp
0x180021bb6  mov     [rbp+37h+var_40], rax
0x180021bba  mov     rax, [rbp+37h+arg_38]
0x180021bbe  mov     esi, edx
0x180021bc0  mov     rbx, [rbp+37h+arg_30]
0x180021bc4  xor     edx, edx; Val
0x180021bc6  mov     rdi, [rbp+37h+arg_28]
0x180021bca  mov     r15d, r8d
0x180021bcd  mov     r12, rcx
0x180021bd0  mov     [rbp+37h+var_A0], rax
0x180021bd4  xorps   xmm0, xmm0
0x180021bd7  lea     rcx, [rbp+37h+var_80]; void *
0x180021bdb  lea     r8d, [rdx+40h]; Size
0x180021bdf  mov     r14d, r9d
0x180021be2  movups  xmmword ptr [rbp+37h+var_98], xmm0
0x180021be6  call    memset_0
0x180021beb  test    rdi, rdi
0x180021bee  jz      loc_180021E0A
0x180021bf4  test    rbx, rbx
0x180021bf7  jz      loc_180021E0A
0x180021bfd  test    esi, esi
0x180021bff  jnz     short loc_180021C0A
0x180021c01  test    r14d, r14d
0x180021c04  jz      loc_180021E0A
0x180021c0a  cmp     r15d, 1
0x180021c0e  jnz     loc_180021E0A
0x180021c14  cmp     [rbp+37h+arg_20], r15d
0x180021c18  jnz     loc_180021E0A
0x180021c1e  mov     eax, [rdi+8]
0x180021c21  mov     [rbp+37h+var_78], eax
0x180021c24  mov     eax, [rbx+8]
0x180021c27  mov     [rbp+37h+var_7C], eax
0x180021c2a  mov     eax, 0A1B2C3D4h
0x180021c2f  mov     [rbp+37h+var_80], 3
0x180021c36  cmp     [rdi], eax
0x180021c38  jnz     loc_180021E04
0x180021c3e  cmp     [rbx], eax
0x180021c40  jnz     loc_180021E04
0x180021c46  xor     edx, edx
0x180021c48  mov     rcx, r12
0x180021c4b  call    SockFindAndReferenceSocket
0x180021c50  mov     rdi, rax
0x180021c53  test    rax, rax
0x180021c56  jnz     short loc_180021C62
0x180021c58  mov     ecx, 2736h
0x180021c5d  jmp     loc_180021E0F
0x180021c62  lea     r13, [rax+0E0h]
0x180021c69  xor     r15d, r15d
0x180021c6c  mov     rcx, r13; lpCriticalSection
0x180021c6f  call    cs:__imp_EnterCriticalSection
0x180021c76  nop     dword ptr [rax+rax+00h]
0x180021c7b  cmp     dword ptr [rdi+18h], 4
0x180021c7f  jz      loc_180021D93
0x180021c85  cmp     dword ptr [rdi+18h], 0FFFFFFFFh
0x180021c89  jz      loc_180021D93
0x180021c8f  inc     esi
0x180021c91  inc     r14d
0x180021c94  mov     ecx, esi
0x180021c96  cmp     dword ptr [rdi+20h], 1
0x180021c9a  mov     edx, r14d
0x180021c9d  setz    r8b
0x180021ca1  xor     r9d, r9d
0x180021ca4  call    AllocateRequestQueue
0x180021ca9  mov     rbx, rax
0x180021cac  test    rax, rax
0x180021caf  jnz     short loc_180021CBB
0x180021cb1  mov     ecx, 2747h
0x180021cb6  jmp     loc_180021D9A
0x180021cbb  lea     eax, [rsi+rsi*8]
0x180021cbe  mov     [rbp+37h+var_60], esi
0x180021cc1  lea     eax, ds:10h[rax*8]
0x180021cc8  mov     [rbp+37h+var_74], r14d
0x180021ccc  mov     [rbp+37h+var_5C], eax
0x180021ccf  lea     eax, [r14+r14*8]
0x180021cd3  lea     eax, ds:10h[rax*8]
0x180021cda  mov     [rbp+37h+var_70], eax
0x180021cdd  mov     rax, [rbx+20h]
0x180021ce1  mov     [rbp+37h+var_68], rax
0x180021ce5  mov     rax, [rbx+28h]
0x180021ce9  mov     [rbp+37h+var_58], rax
0x180021ced  mov     rax, [rbp+37h+var_A0]
0x180021cf1  mov     [rbp+37h+var_48], rax
0x180021cf5  mov     rax, cs:MswRioRegDomain
0x180021cfc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021d00  jnz     short loc_180021D07
0x180021d02  call    CreateRegDomain
0x180021d07  mov     [rsp+0F0h+OutputBufferLength], r15d; OutputBufferLength
0x180021d0c  xor     r9d, r9d; ApcContext
0x180021d0f  mov     [rsp+0F0h+OutputBuffer], r15; OutputBuffer
0x180021d14  xor     r8d, r8d; ApcRoutine
0x180021d17  mov     [rbp+37h+var_50], rax
0x180021d1b  xor     edx, edx; Event
0x180021d1d  mov     [rsp+0F0h+InputBufferLength], 40h ; '@'; InputBufferLength
0x180021d25  lea     rax, [rbp+37h+var_80]
0x180021d29  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x180021d2e  mov     rcx, r12; FileHandle
0x180021d31  lea     rax, [rbp+37h+var_98]
0x180021d35  mov     [rsp+0F0h+IoControlCode], 1211Bh; IoControlCode
0x180021d3d  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x180021d42  call    cs:__imp_NtDeviceIoControlFile
0x180021d49  nop     dword ptr [rax+rax+00h]
0x180021d4e  cmp     eax, 103h
0x180021d53  jz      loc_180021E04
0x180021d59  test    eax, eax
0x180021d5b  js      short loc_180021D6C
0x180021d5d  mov     [rdi+10h], rbx
0x180021d61  mov     r15, rbx
0x180021d64  mov     [rbx+8], r12
0x180021d68  xor     ebx, ebx
0x180021d6a  jmp     short loc_180021DA6
0x180021d6c  cmp     eax, 0C00000CEh
0x180021d71  jz      loc_180021CB1
0x180021d77  cmp     eax, 0C0000010h
0x180021d7c  jnz     short loc_180021D85
0x180021d7e  mov     ecx, 273Dh
0x180021d83  jmp     short loc_180021D9A
0x180021d85  cmp     eax, 0C000000Dh
0x180021d8a  jz      short loc_180021D95
0x180021d8c  mov     ecx, 271Eh
0x180021d91  jmp     short loc_180021D9A
0x180021d93  xor     ebx, ebx
0x180021d95  mov     ecx, 2726h; dwErrCode
0x180021d9a  call    cs:__imp_SetLastError
0x180021da1  nop     dword ptr [rax+rax+00h]
0x180021da6  mov     rcx, r13; lpCriticalSection
0x180021da9  call    cs:__imp_LeaveCriticalSection
0x180021db0  nop     dword ptr [rax+rax+00h]
0x180021db5  or      eax, 0FFFFFFFFh
0x180021db8  lock xadd [rdi], eax
0x180021dbc  cmp     eax, 1
0x180021dbf  jnz     short loc_180021DC9
0x180021dc1  mov     rcx, rdi
0x180021dc4  call    SockDestroySocket
0x180021dc9  test    rbx, rbx
0x180021dcc  jz      short loc_180021DFF
0x180021dce  mov     r8, [rbx+20h]; P
0x180021dd2  xor     edx, edx; Flags
0x180021dd4  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180021ddb  call    cs:__imp_RtlFreeHeap
0x180021de2  nop     dword ptr [rax+rax+00h]
0x180021de7  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180021dee  mov     r8, rbx; P
0x180021df1  xor     edx, edx; Flags
0x180021df3  call    cs:__imp_RtlFreeHeap
0x180021dfa  nop     dword ptr [rax+rax+00h]
0x180021dff  mov     rax, r15
0x180021e02  jmp     short loc_180021E1D
0x180021e04  call    RioException
0x180021e0a  mov     ecx, 2726h; dwErrCode
0x180021e0f  call    cs:__imp_SetLastError
0x180021e16  nop     dword ptr [rax+rax+00h]
0x180021e1b  xor     eax, eax
0x180021e1d  mov     rcx, [rbp+37h+var_40]
0x180021e21  xor     rcx, rsp; StackCookie
0x180021e24  call    __security_check_cookie
0x180021e29  mov     rbx, [rsp+0F0h+arg_10]
0x180021e31  add     rsp, 0C0h
0x180021e38  pop     r15
0x180021e3a  pop     r14
0x180021e3c  pop     r13
0x180021e3e  pop     r12
0x180021e40  pop     rdi
0x180021e41  pop     rsi
0x180021e42  pop     rbp
0x180021e43  retn
```
