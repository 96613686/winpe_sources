# CreateOMIError_shared

- ea: `0x180042c5c`
- end: `0x180042dc4`
- name: `CreateOMIError_shared`
- size: `360`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, MI_Instance **extendedError)`
- caller_count: `15`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007c80`
- `0x180008db0`
- `0x180008ea0`
- `0x180008f20`
- `0x180008fb0`
- `0x18001936c`
- `0x1800283d0`
- `0x180029f50`
- `0x18002a9c0`
- `0x18002c558`
- `0x180032560`
- `0x1800386f0`
- `0x18003dd00`
- `0x18003f858`
- `0x180042a1c`

## callees

- `0x180042c5c`
- `0x180045010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x180042ca2`
- `mi!MI_Application_InitializeV1` at `0x180042ca2`

## pseudocode

```c
MI_Result __fastcall CreateOMIError_shared(
        MI_Instance **a1,
        int a2,
        MI_Instance **a3,
        __int16 a4,
        __int64 a5,
        MI_Instance **extendedError)
{
  MI_Instance **v6; // rdi
  MI_Result result; // eax
  int v12; // eax
  MI_Instance *v13; // rcx
  int v14; // ebx
  MI_Instance *v15; // rax
  MI_Instance *v16; // rax
  MI_Instance *v17; // rax
  MI_Instance *v18; // [rsp+30h] [rbp-20h] BYREF
  MI_Application application; // [rsp+38h] [rbp-18h] BYREF

  v6 = extendedError;
  v18 = 0;
  application.ft = 0;
  *extendedError = 0;
  *(_OWORD *)&application.reserved1 = 0;
  result = MI_Application_InitializeV1(0, 0, v6, &application);
  if ( result )
    return result;
  if ( !application.ft )
  {
    v13 = 0;
    v18 = 0;
    v14 = 4;
    goto LABEL_9;
  }
  v12 = ((__int64 (__fastcall *)(MI_Application *, _QWORD, __int64, MI_Instance **))application.ft->NewInstance)(
          &application,
          *(_QWORD *)(a5 + 8),
          a5,
          &v18);
  v13 = v18;
  v14 = v12;
  if ( v12 )
  {
LABEL_9:
    if ( v13 && v13->ft )
      ((void (__fastcall *)(MI_Instance *))v13->ft->Delete)(v13);
    goto LABEL_12;
  }
  extendedError = a1;
  v14 = ((__int64 (__fastcall *)(MI_Instance *, __int64, MI_Instance ***, __int64, _DWORD))v18->ft->SetElementAt)(
          v18,
          4,
          &extendedError,
          13,
          0);
  if ( v14
    || (v15 = v18,
        extendedError = a3,
        LODWORD(v18[4].serverName) = a2,
        BYTE4(v15[4].serverName) = 1,
        (v14 = ((__int64 (__fastcall *)(MI_Instance *, __int64, MI_Instance ***, __int64, _DWORD))v18->ft->SetElementAt)(
                 v18,
                 16,
                 &extendedError,
                 13,
                 0)) != 0) )
  {
    v13 = v18;
    goto LABEL_9;
  }
  v16 = v18;
  LOWORD(v18[4].reserved[1]) = a4;
  BYTE2(v16[4].reserved[1]) = 1;
  v17 = v18;
  LODWORD(v18[3].reserved[3]) = 1;
  BYTE4(v17[3].reserved[3]) = 1;
  *v6 = v18;
LABEL_12:
  if ( application.ft )
    ((void (__fastcall *)(MI_Application *))application.ft->Close)(&application);
  return v14;
}

```

## disassembly

```asm
0x180042c5c  push    rbp
0x180042c5e  push    rbx
0x180042c5f  push    rsi
0x180042c60  push    rdi
0x180042c61  push    r12
0x180042c63  push    r14
0x180042c65  push    r15
0x180042c67  mov     rbp, rsp
0x180042c6a  sub     rsp, 50h
0x180042c6e  mov     rdi, [rbp+extendedError]
0x180042c72  xor     eax, eax
0x180042c74  movzx   esi, r9w
0x180042c78  mov     [rbp+var_20], 0
0x180042c80  mov     r15, r8
0x180042c83  mov     [rbp+application.ft], rax
0x180042c87  mov     r12d, edx
0x180042c8a  lea     r9, [rbp+application]; application
0x180042c8e  mov     r14, rcx
0x180042c91  mov     [rdi], rax
0x180042c94  xorps   xmm0, xmm0
0x180042c97  mov     r8, rdi; extendedError
0x180042c9a  xor     edx, edx; applicationID
0x180042c9c  xor     ecx, ecx; flags
0x180042c9e  movups  xmmword ptr [rbp+application.reserved1], xmm0
0x180042ca2  call    cs:__imp_MI_Application_InitializeV1
0x180042ca8  test    eax, eax
0x180042caa  jnz     loc_180042DB5
0x180042cb0  mov     rax, [rbp+application.ft]
0x180042cb4  test    rax, rax
0x180042cb7  jz      loc_180042D7F
0x180042cbd  mov     rdx, [rbp+arg_20]
0x180042cc1  lea     r9, [rbp+var_20]
0x180042cc5  mov     rax, [rax+18h]
0x180042cc9  lea     rcx, [rbp+application]
0x180042ccd  mov     r8, rdx
0x180042cd0  mov     rdx, [rdx+8]
0x180042cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cd9  mov     rcx, [rbp+var_20]
0x180042cdd  mov     ebx, eax
0x180042cdf  test    eax, eax
0x180042ce1  jnz     loc_180042D88
0x180042ce7  mov     [rbp+extendedError], r14
0x180042ceb  lea     r8, [rbp+extendedError]
0x180042cef  mov     rax, [rcx]
0x180042cf2  lea     r14d, [rbx+0Dh]
0x180042cf6  mov     r9d, r14d
0x180042cf9  mov     [rsp+50h+var_30], ebx
0x180042cfd  lea     edx, [rbx+4]
0x180042d00  mov     rax, [rax+50h]
0x180042d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d09  mov     ebx, eax
0x180042d0b  test    eax, eax
0x180042d0d  jnz     short loc_180042D79
0x180042d0f  mov     rax, [rbp+var_20]
0x180042d13  lea     r8, [rbp+extendedError]
0x180042d17  mov     [rbp+extendedError], r15
0x180042d1b  lea     edx, [rbx+10h]
0x180042d1e  mov     r9d, r14d
0x180042d21  mov     [rsp+50h+var_30], ebx
0x180042d25  mov     [rax+110h], r12d
0x180042d2c  mov     byte ptr [rax+114h], 1
0x180042d33  mov     rcx, [rbp+var_20]
0x180042d37  mov     rax, [rcx]
0x180042d3a  mov     rax, [rax+50h]
0x180042d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d43  mov     ebx, eax
0x180042d45  test    eax, eax
0x180042d47  jnz     short loc_180042D79
0x180042d49  mov     rax, [rbp+var_20]
0x180042d4d  mov     [rax+128h], si
0x180042d54  mov     byte ptr [rax+12Ah], 1
0x180042d5b  mov     rax, [rbp+var_20]
0x180042d5f  mov     dword ptr [rax+0F8h], 1
0x180042d69  mov     byte ptr [rax+0FCh], 1
0x180042d70  mov     rax, [rbp+var_20]
0x180042d74  mov     [rdi], rax
0x180042d77  jmp     short loc_180042D9E
0x180042d79  mov     rcx, [rbp+var_20]
0x180042d7d  jmp     short loc_180042D88
0x180042d7f  xor     ecx, ecx
0x180042d81  mov     [rbp+var_20], rcx
0x180042d85  lea     ebx, [rcx+4]
0x180042d88  test    rcx, rcx
0x180042d8b  jz      short loc_180042D9E
0x180042d8d  mov     rax, [rcx]
0x180042d90  test    rax, rax
0x180042d93  jz      short loc_180042D9E
0x180042d95  mov     rax, [rax+10h]
0x180042d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d9e  mov     rax, [rbp+application.ft]
0x180042da2  test    rax, rax
0x180042da5  jz      short loc_180042DB3
0x180042da7  mov     rax, [rax]
0x180042daa  lea     rcx, [rbp+application]
0x180042dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042db3  mov     eax, ebx
0x180042db5  add     rsp, 50h
0x180042db9  pop     r15
0x180042dbb  pop     r14
0x180042dbd  pop     r12
0x180042dbf  pop     rdi
0x180042dc0  pop     rsi
0x180042dc1  pop     rbx
0x180042dc2  pop     rbp
0x180042dc3  retn
```
