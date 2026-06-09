# ShutdownProcesses

- ea: `0x180006a80`
- end: `0x180006d0b`
- name: `ShutdownProcesses`
- size: `651`
- prototype: `__int64 __fastcall(_DWORD *, int, int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180007060`

## callees

- `0x180003bb0`
- `0x180006a80`
- `0x180006d20`
- `0x180006df0`
- `0x180006ea0`
- `0x18000ab61`
- `0x18000ab80`
- `0x18000b010`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x180006ac9`
- `ntdll!RtlEnterCriticalSection` at `0x180006c3b`
- `ntdll!RtlEnterCriticalSection` at `0x180006ac9`
- `ntdll!RtlEnterCriticalSection` at `0x180006c3b`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180006bb8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006bfc`
- `ntdll!RtlLeaveCriticalSection` at `0x180006b0c`
- `ntdll!RtlLeaveCriticalSection` at `0x180006bb8`
- `ntdll!RtlLeaveCriticalSection` at `0x180006bfc`

## pseudocode

```c
__int64 __fastcall ShutdownProcesses(_DWORD *a1, int a2, int a3, __int64 a4)
{
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // esi
  __int64 v12; // rbx
  char v13; // r14
  char v14; // r15
  unsigned int *v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 i; // rdi
  __int64 v23; // rbp
  __int64 v24; // rcx
  __int64 v25; // rdi
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // rdx
  unsigned int v29; // edx
  int v30; // [rsp+20h] [rbp-478h]
  _DWORD v31[68]; // [rsp+40h] [rbp-458h] BYREF
  _QWORD v32[64]; // [rsp+150h] [rbp-348h] BYREF
  _DWORD v33[64]; // [rsp+350h] [rbp-148h] BYREF

  memset_0(v32, 0, sizeof(v32));
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  v8 = 1;
  if ( !a3 )
    v8 = 64;
  v31[0] = v8;
  FindProcessesForShutdown(v32, v31, a4);
  v10 = v31[0];
  if ( !v31[0] )
  {
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    return 2147483674LL;
  }
  v12 = 0;
  v13 = 0;
  v14 = 1;
  do
  {
    v15 = (unsigned int *)v32[v12];
    v16 = *v15;
    v17 = v15[31];
    v18 = v15[30];
    v31[v12 + 4] = v16;
    CsrEventWriteULONG3(v9, v16, v18, v17);
    v12 = (unsigned int)(v12 + 1);
  }
  while ( (unsigned int)v12 < v10 );
  while ( 1 )
  {
    v19 = 0;
    do
    {
      v20 = CsrLoadedServerDll[v19];
      if ( !v20 || !*(_QWORD *)(v20 + 112) )
        goto LABEL_10;
      RtlLeaveCriticalSection(&CsrProcessStructureLock);
      LOBYTE(v30) = v14;
      (*(void (__fastcall **)(_QWORD *, _DWORD *, _QWORD, _QWORD, int, int))(v20 + 112))(
        v32,
        v33,
        v10,
        (unsigned int)*a1,
        v30,
        a2);
      v23 = 0;
      RtlEnterCriticalSection(&CsrProcessStructureLock);
      v25 = 0;
      if ( v10 )
      {
        while ( 1 )
        {
          v26 = v33[v25];
          if ( v26 == 1 )
            goto LABEL_16;
          if ( v26 == 4 )
            break;
          v29 = v31[v25 + 4];
          if ( v26 != 3 )
          {
            v32[v23] = v32[v25];
            v31[v23 + 4] = v29;
            v23 = (unsigned int)(v23 + 1);
            goto LABEL_18;
          }
          v27 = v29;
          v13 = 1;
          v28 = 3221225760LL;
LABEL_17:
          CsrEventWriteULONG2(v24, v28, v27);
LABEL_18:
          v25 = (unsigned int)(v25 + 1);
          if ( (unsigned int)v25 >= v10 )
            goto LABEL_19;
        }
        *a1 |= 0x24u;
LABEL_16:
        v27 = (unsigned int)v31[v25 + 4];
        v28 = 0;
        goto LABEL_17;
      }
LABEL_19:
      v10 = v23;
      if ( !(_DWORD)v23 )
        goto LABEL_12;
      if ( v13 )
        break;
LABEL_10:
      v19 = (unsigned int)(v19 + 1);
    }
    while ( (unsigned int)v19 < 6 );
    if ( !v10 || !v14 || v13 )
      break;
    v14 = 0;
  }
LABEL_12:
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
  {
    CsrEventWriteULONG2(v21, 3221226021LL, (unsigned int)v31[i + 4]);
    CsrDereferenceProcess(v32[i]);
  }
  return v13 != 0 ? 0xC0000120 : 0;
}

```

## disassembly

```asm
0x180006a80  push    rbx
0x180006a82  push    rsi
0x180006a83  push    rdi
0x180006a84  push    r12
0x180006a86  push    r13
0x180006a88  sub     rsp, 470h
0x180006a8f  mov     rax, cs:__security_cookie
0x180006a96  xor     rax, rsp
0x180006a99  mov     [rsp+498h+var_48], rax
0x180006aa1  mov     ebx, r8d
0x180006aa4  mov     r13d, edx
0x180006aa7  mov     r12, rcx
0x180006aaa  xor     edx, edx; Val
0x180006aac  mov     r8d, 200h; Size
0x180006ab2  lea     rcx, [rsp+498h+var_348]; void *
0x180006aba  mov     rdi, r9
0x180006abd  call    memset_0
0x180006ac2  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180006ac9  call    cs:__imp_RtlEnterCriticalSection
0x180006ad0  nop     dword ptr [rax+rax+00h]
0x180006ad5  mov     eax, 1
0x180006ada  lea     rcx, [rsp+498h+var_348]
0x180006ae2  mov     edx, 40h ; '@'
0x180006ae7  test    ebx, ebx
0x180006ae9  mov     r8, rdi
0x180006aec  cmovz   eax, edx
0x180006aef  lea     rdx, [rsp+498h+var_458]
0x180006af4  mov     [rsp+498h+var_458], eax
0x180006af8  call    FindProcessesForShutdown
0x180006afd  mov     esi, [rsp+498h+var_458]
0x180006b01  test    esi, esi
0x180006b03  jnz     short loc_180006B3D
0x180006b05  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180006b0c  call    cs:__imp_RtlLeaveCriticalSection
0x180006b13  nop     dword ptr [rax+rax+00h]
0x180006b18  mov     eax, 8000001Ah
0x180006b1d  mov     rcx, [rsp+498h+var_48]
0x180006b25  xor     rcx, rsp; StackCookie
0x180006b28  call    __security_check_cookie
0x180006b2d  add     rsp, 470h
0x180006b34  pop     r13
0x180006b36  pop     r12
0x180006b38  pop     rdi
0x180006b39  pop     rsi
0x180006b3a  pop     rbx
0x180006b3b  retn
0x180006b3d  mov     [rsp+498h+arg_10], rbp
0x180006b45  xor     ebx, ebx
0x180006b47  mov     [rsp+498h+var_30], r14
0x180006b4f  xor     r14b, r14b
0x180006b52  mov     [rsp+498h+var_38], r15
0x180006b5a  mov     r15b, 1
0x180006b5d  test    esi, esi
0x180006b5f  jz      short loc_180006B83
0x180006b61  mov     r8, [rsp+rbx*8+498h+var_348]
0x180006b69  mov     edx, [r8]
0x180006b6c  mov     r9d, [r8+7Ch]
0x180006b70  mov     r8d, [r8+78h]
0x180006b74  mov     [rsp+rbx*4+498h+var_448], edx
0x180006b78  call    CsrEventWriteULONG3
0x180006b7d  inc     ebx
0x180006b7f  cmp     ebx, esi
0x180006b81  jb      short loc_180006B61
0x180006b83  lea     rcx, CsrLoadedServerDll
0x180006b8a  nop     word ptr [rax+rax+00h]
0x180006b90  xor     ebx, ebx
0x180006b92  mov     rdi, [rcx+rbx*8]
0x180006b96  test    rdi, rdi
0x180006b99  jz      short loc_180006BA2
0x180006b9b  cmp     qword ptr [rdi+70h], 0
0x180006ba0  jnz     short loc_180006BF5
0x180006ba2  inc     ebx
0x180006ba4  cmp     ebx, 6
0x180006ba7  jb      short loc_180006B92
0x180006ba9  test    esi, esi
0x180006bab  jnz     loc_180006CC0
0x180006bb1  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180006bb8  call    cs:__imp_RtlLeaveCriticalSection
0x180006bbf  nop     dword ptr [rax+rax+00h]
0x180006bc4  mov     r15, [rsp+498h+var_38]
0x180006bcc  xor     edi, edi
0x180006bce  mov     rbp, [rsp+498h+arg_10]
0x180006bd6  test    esi, esi
0x180006bd8  jnz     loc_180006CE4
0x180006bde  neg     r14b
0x180006be1  mov     r14, [rsp+498h+var_30]
0x180006be9  sbb     eax, eax
0x180006beb  and     eax, 0C0000120h
0x180006bf0  jmp     loc_180006B1D
0x180006bf5  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180006bfc  call    cs:__imp_RtlLeaveCriticalSection
0x180006c03  nop     dword ptr [rax+rax+00h]
0x180006c08  mov     r9d, [r12]
0x180006c0c  lea     rdx, [rsp+498h+var_148]
0x180006c14  mov     rax, [rdi+70h]
0x180006c18  lea     rcx, [rsp+498h+var_348]
0x180006c20  mov     r8d, esi
0x180006c23  mov     [rsp+498h+var_470], r13d
0x180006c28  mov     [rsp+498h+var_478], r15b
0x180006c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c32  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180006c39  xor     ebp, ebp
0x180006c3b  call    cs:__imp_RtlEnterCriticalSection
0x180006c42  nop     dword ptr [rax+rax+00h]
0x180006c47  xor     edi, edi
0x180006c49  test    esi, esi
0x180006c4b  jz      short loc_180006C6E
0x180006c4d  nop     dword ptr [rax]
0x180006c50  mov     eax, [rsp+rdi*4+498h+var_148]
0x180006c57  cmp     eax, 1
0x180006c5a  jnz     short loc_180006C8D
0x180006c5c  mov     r8d, [rsp+rdi*4+498h+var_448]
0x180006c61  xor     edx, edx
0x180006c63  call    CsrEventWriteULONG2
0x180006c68  inc     edi
0x180006c6a  cmp     edi, esi
0x180006c6c  jb      short loc_180006C50
0x180006c6e  mov     esi, ebp
0x180006c70  test    ebp, ebp
0x180006c72  jz      loc_180006BB1
0x180006c78  test    r14b, r14b
0x180006c7b  jnz     loc_180006BA9
0x180006c81  lea     rcx, CsrLoadedServerDll
0x180006c88  jmp     loc_180006BA2
0x180006c8d  cmp     eax, 4
0x180006c90  jz      short loc_180006CDA
0x180006c92  mov     edx, [rsp+rdi*4+498h+var_448]
0x180006c96  cmp     eax, 3
0x180006c99  jnz     short loc_180006CA8
0x180006c9b  mov     r8d, edx
0x180006c9e  mov     r14b, 1
0x180006ca1  mov     edx, 0C0000120h
0x180006ca6  jmp     short loc_180006C63
0x180006ca8  mov     rax, [rsp+rdi*8+498h+var_348]
0x180006cb0  mov     [rsp+rbp*8+498h+var_348], rax
0x180006cb8  mov     [rsp+rbp*4+498h+var_448], edx
0x180006cbc  inc     ebp
0x180006cbe  jmp     short loc_180006C68
0x180006cc0  test    r15b, r15b
0x180006cc3  jz      loc_180006BB1
0x180006cc9  test    r14b, r14b
0x180006ccc  jnz     loc_180006BB1
0x180006cd2  xor     r15b, r15b
0x180006cd5  jmp     loc_180006B83
0x180006cda  or      dword ptr [r12], 24h
0x180006cdf  jmp     loc_180006C5C
0x180006ce4  mov     r8d, [rsp+rdi*4+498h+var_448]
0x180006ce9  mov     edx, 0C0000225h
0x180006cee  call    CsrEventWriteULONG2
0x180006cf3  mov     rcx, [rsp+rdi*8+498h+var_348]
0x180006cfb  call    CsrDereferenceProcess
0x180006d00  inc     edi
0x180006d02  cmp     edi, esi
0x180006d04  jb      short loc_180006CE4
0x180006d06  jmp     loc_180006BDE
```
