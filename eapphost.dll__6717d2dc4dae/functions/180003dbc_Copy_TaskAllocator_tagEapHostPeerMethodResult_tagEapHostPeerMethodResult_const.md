# Copy<TaskAllocator>(tagEapHostPeerMethodResult &,tagEapHostPeerMethodResult const &)

- ea: `0x180003dbc`
- end: `0x180003f0e`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAUtagEapHostPeerMethodResult@@AEBU0@@Z`
- size: `338`
- prototype: `char __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006970`

## callees

- `0x18000343c`
- `0x180003a4c`
- `0x180003c40`
- `0x180003cec`
- `0x180003dbc`
- `0x1800040d0`
- `0x180033d78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ea3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003de5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ea3`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(_DWORD *a1, __int64 a2)
{
  void *v4; // rax
  char v5; // di
  void *v6; // rax
  LPVOID v7; // rax
  LPVOID v8; // rax
  _OWORD *v9; // rax

  memset_0(a1, 0, 0x48u);
  if ( !*(_DWORD *)(a2 + 12) )
  {
LABEL_5:
    if ( *(_DWORD *)(a2 + 28) )
    {
      v6 = CoTaskMemAlloc(*(unsigned int *)(a2 + 28));
      *((_QWORD *)a1 + 4) = v6;
      if ( !v6 )
        goto LABEL_3;
      memcpy_0(v6, *(const void **)(a2 + 32), *(unsigned int *)(a2 + 28));
    }
    v5 = 1;
    if ( *(_QWORD *)(a2 + 40) )
    {
      v7 = CoTaskMemAlloc(0x10u);
      *((_QWORD *)a1 + 5) = v7;
      if ( !v7 )
        goto LABEL_3;
      v5 = Copy<TaskAllocator>((__int64)v7, *(_DWORD **)(a2 + 40));
      if ( !v5 )
        goto LABEL_17;
    }
    if ( *(_QWORD *)(a2 + 56) )
    {
      v8 = CoTaskMemAlloc(0x30u);
      *((_QWORD *)a1 + 7) = v8;
      if ( !v8 )
        goto LABEL_3;
      v5 = Copy<TaskAllocator>((__int64)v8, *(_QWORD *)(a2 + 56));
      if ( !v5 )
        goto LABEL_17;
    }
    if ( *(_QWORD *)(a2 + 64) )
    {
      v9 = CoTaskMemAlloc(0x58u);
      *((_QWORD *)a1 + 8) = v9;
      if ( !v9 )
        goto LABEL_3;
      v5 = Copy<TaskAllocator>(v9, *(_QWORD *)(a2 + 64));
      if ( !v5 )
        goto LABEL_17;
    }
    *a1 = *(_DWORD *)a2;
    a1[1] = *(_DWORD *)(a2 + 4);
    a1[2] = *(_DWORD *)(a2 + 8);
    a1[3] = *(_DWORD *)(a2 + 12);
    a1[6] = *(_DWORD *)(a2 + 24);
    a1[7] = *(_DWORD *)(a2 + 28);
    a1[12] = *(_DWORD *)(a2 + 48);
    return v5;
  }
  v4 = CoTaskMemAlloc(*(unsigned int *)(a2 + 12));
  *((_QWORD *)a1 + 2) = v4;
  if ( v4 )
  {
    memcpy_0(v4, *(const void **)(a2 + 16), *(unsigned int *)(a2 + 12));
    goto LABEL_5;
  }
LABEL_3:
  v5 = 0;
LABEL_17:
  Free<TaskAllocator>(a1);
  return v5;
}

```

## disassembly

```asm
0x180003dbc  mov     [rsp+arg_0], rbx
0x180003dc1  mov     [rsp+arg_8], rsi
0x180003dc6  push    rdi
0x180003dc7  sub     rsp, 20h
0x180003dcb  mov     rbx, rdx
0x180003dce  mov     rsi, rcx
0x180003dd1  xor     edx, edx; Val
0x180003dd3  lea     r8d, [rdx+48h]; Size
0x180003dd7  call    memset_0
0x180003ddc  cmp     dword ptr [rbx+0Ch], 0
0x180003de0  jbe     short loc_180003E0C
0x180003de2  mov     ecx, [rbx+0Ch]; cb
0x180003de5  call    cs:__imp_CoTaskMemAlloc
0x180003deb  mov     [rsi+10h], rax
0x180003def  test    rax, rax
0x180003df2  jnz     short loc_180003DFC
0x180003df4  xor     dil, dil
0x180003df7  jmp     loc_180003EC9
0x180003dfc  mov     r8d, [rbx+0Ch]; Size
0x180003e00  mov     rdx, [rbx+10h]; Src
0x180003e04  mov     rcx, rax; void *
0x180003e07  call    memcpy_0
0x180003e0c  cmp     dword ptr [rbx+1Ch], 0
0x180003e10  jbe     short loc_180003E34
0x180003e12  mov     ecx, [rbx+1Ch]; cb
0x180003e15  call    cs:__imp_CoTaskMemAlloc
0x180003e1b  mov     [rsi+20h], rax
0x180003e1f  test    rax, rax
0x180003e22  jz      short loc_180003DF4
0x180003e24  mov     r8d, [rbx+1Ch]; Size
0x180003e28  mov     rdx, [rbx+20h]; Src
0x180003e2c  mov     rcx, rax; void *
0x180003e2f  call    memcpy_0
0x180003e34  mov     dil, 1
0x180003e37  cmp     qword ptr [rbx+28h], 0
0x180003e3c  jz      short loc_180003E65
0x180003e3e  mov     ecx, 10h; cb
0x180003e43  call    cs:__imp_CoTaskMemAlloc
0x180003e49  mov     [rsi+28h], rax
0x180003e4d  test    rax, rax
0x180003e50  jz      short loc_180003DF4
0x180003e52  mov     rdx, [rbx+28h]
0x180003e56  mov     rcx, rax
0x180003e59  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x180003e5e  mov     dil, al
0x180003e61  test    al, al
0x180003e63  jz      short loc_180003EC9
0x180003e65  cmp     qword ptr [rbx+38h], 0
0x180003e6a  jz      short loc_180003E97
0x180003e6c  mov     ecx, 30h ; '0'; cb
0x180003e71  call    cs:__imp_CoTaskMemAlloc
0x180003e77  mov     [rsi+38h], rax
0x180003e7b  test    rax, rax
0x180003e7e  jz      loc_180003DF4
0x180003e84  mov     rdx, [rbx+38h]
0x180003e88  mov     rcx, rax
0x180003e8b  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x180003e90  mov     dil, al
0x180003e93  test    al, al
0x180003e95  jz      short loc_180003EC9
0x180003e97  cmp     qword ptr [rbx+40h], 0
0x180003e9c  jz      short loc_180003ED3
0x180003e9e  mov     ecx, 58h ; 'X'; cb
0x180003ea3  call    cs:__imp_CoTaskMemAlloc
0x180003ea9  mov     [rsi+40h], rax
0x180003ead  test    rax, rax
0x180003eb0  jz      loc_180003DF4
0x180003eb6  mov     rdx, [rbx+40h]
0x180003eba  mov     rcx, rax; void *
0x180003ebd  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180003ec2  mov     dil, al
0x180003ec5  test    al, al
0x180003ec7  jnz     short loc_180003ED3
0x180003ec9  mov     rcx, rsi; void *
0x180003ecc  call    ??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z; Free<TaskAllocator>(tagEapHostPeerMethodResult &)
0x180003ed1  jmp     short loc_180003EFB
0x180003ed3  mov     eax, [rbx]
0x180003ed5  mov     [rsi], eax
0x180003ed7  mov     eax, [rbx+4]
0x180003eda  mov     [rsi+4], eax
0x180003edd  mov     eax, [rbx+8]
0x180003ee0  mov     [rsi+8], eax
0x180003ee3  mov     eax, [rbx+0Ch]
0x180003ee6  mov     [rsi+0Ch], eax
0x180003ee9  mov     eax, [rbx+18h]
0x180003eec  mov     [rsi+18h], eax
0x180003eef  mov     eax, [rbx+1Ch]
0x180003ef2  mov     [rsi+1Ch], eax
0x180003ef5  mov     eax, [rbx+30h]
0x180003ef8  mov     [rsi+30h], eax
0x180003efb  mov     al, dil
0x180003efe  mov     rbx, [rsp+28h+arg_0]
0x180003f03  mov     rsi, [rsp+28h+arg_8]
0x180003f08  add     rsp, 20h
0x180003f0c  pop     rdi
0x180003f0d  retn
```
