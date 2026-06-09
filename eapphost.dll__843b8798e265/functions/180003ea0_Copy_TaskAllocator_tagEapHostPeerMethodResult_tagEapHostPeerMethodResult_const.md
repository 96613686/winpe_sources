# Copy<TaskAllocator>(tagEapHostPeerMethodResult &,tagEapHostPeerMethodResult const &)

- ea: `0x180003ea0`
- end: `0x180004011`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAUtagEapHostPeerMethodResult@@AEBU0@@Z`
- size: `369`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006c00`

## callees

- `0x1800034cc`
- `0x180003b00`
- `0x180003d0c`
- `0x180003dc8`
- `0x180003ea0`
- `0x180004204`
- `0x180035138`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003ec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003f9f`

## pseudocode

```c
char __fastcall Copy<TaskAllocator>(_DWORD *a1, __int64 a2)
{
  void *v4; // rax
  char v5; // di
  void *v6; // rax
  LPVOID v7; // rax
  LPVOID v8; // rax
  void *v9; // rax

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
      v5 = Copy<TaskAllocator>(v7, *(_QWORD *)(a2 + 40));
      if ( !v5 )
        goto LABEL_17;
    }
    if ( *(_QWORD *)(a2 + 56) )
    {
      v8 = CoTaskMemAlloc(0x30u);
      *((_QWORD *)a1 + 7) = v8;
      if ( !v8 )
        goto LABEL_3;
      v5 = Copy<TaskAllocator>(v8, *(_QWORD *)(a2 + 56));
      if ( !v5 )
        goto LABEL_17;
    }
    if ( *(_QWORD *)(a2 + 64) )
    {
      v9 = CoTaskMemAlloc(0x58u);
      *((_QWORD *)a1 + 8) = v9;
      if ( !v9 )
        goto LABEL_3;
      v5 = Copy<TaskAllocator>(v9);
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
0x180003ea0  mov     [rsp+arg_0], rbx
0x180003ea5  mov     [rsp+arg_8], rsi
0x180003eaa  push    rdi
0x180003eab  sub     rsp, 20h
0x180003eaf  mov     rbx, rdx
0x180003eb2  mov     rsi, rcx
0x180003eb5  xor     edx, edx; Val
0x180003eb7  lea     r8d, [rdx+48h]; Size
0x180003ebb  call    memset_0
0x180003ec0  cmp     dword ptr [rbx+0Ch], 0
0x180003ec4  jbe     short loc_180003EF6
0x180003ec6  mov     ecx, [rbx+0Ch]; cb
0x180003ec9  call    cs:__imp_CoTaskMemAlloc
0x180003ed0  nop     dword ptr [rax+rax+00h]
0x180003ed5  mov     [rsi+10h], rax
0x180003ed9  test    rax, rax
0x180003edc  jnz     short loc_180003EE6
0x180003ede  xor     dil, dil
0x180003ee1  jmp     loc_180003FCB
0x180003ee6  mov     r8d, [rbx+0Ch]; Size
0x180003eea  mov     rdx, [rbx+10h]; Src
0x180003eee  mov     rcx, rax; void *
0x180003ef1  call    memcpy_0
0x180003ef6  cmp     dword ptr [rbx+1Ch], 0
0x180003efa  jbe     short loc_180003F24
0x180003efc  mov     ecx, [rbx+1Ch]; cb
0x180003eff  call    cs:__imp_CoTaskMemAlloc
0x180003f06  nop     dword ptr [rax+rax+00h]
0x180003f0b  mov     [rsi+20h], rax
0x180003f0f  test    rax, rax
0x180003f12  jz      short loc_180003EDE
0x180003f14  mov     r8d, [rbx+1Ch]; Size
0x180003f18  mov     rdx, [rbx+20h]; Src
0x180003f1c  mov     rcx, rax; void *
0x180003f1f  call    memcpy_0
0x180003f24  mov     dil, 1
0x180003f27  cmp     qword ptr [rbx+28h], 0
0x180003f2c  jz      short loc_180003F5B
0x180003f2e  mov     ecx, 10h; cb
0x180003f33  call    cs:__imp_CoTaskMemAlloc
0x180003f3a  nop     dword ptr [rax+rax+00h]
0x180003f3f  mov     [rsi+28h], rax
0x180003f43  test    rax, rax
0x180003f46  jz      short loc_180003EDE
0x180003f48  mov     rdx, [rbx+28h]
0x180003f4c  mov     rcx, rax
0x180003f4f  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ATTRIBUTES@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ATTRIBUTES &,_EAP_ATTRIBUTES const &)
0x180003f54  mov     dil, al
0x180003f57  test    al, al
0x180003f59  jz      short loc_180003FCB
0x180003f5b  cmp     qword ptr [rbx+38h], 0
0x180003f60  jz      short loc_180003F93
0x180003f62  mov     ecx, 30h ; '0'; cb
0x180003f67  call    cs:__imp_CoTaskMemAlloc
0x180003f6e  nop     dword ptr [rax+rax+00h]
0x180003f73  mov     [rsi+38h], rax
0x180003f77  test    rax, rax
0x180003f7a  jz      loc_180003EDE
0x180003f80  mov     rdx, [rbx+38h]
0x180003f84  mov     rcx, rax
0x180003f87  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_METHOD_INFO@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_METHOD_INFO &,_EAP_METHOD_INFO const &)
0x180003f8c  mov     dil, al
0x180003f8f  test    al, al
0x180003f91  jz      short loc_180003FCB
0x180003f93  cmp     qword ptr [rbx+40h], 0
0x180003f98  jz      short loc_180003FD5
0x180003f9a  mov     ecx, 58h ; 'X'; cb
0x180003f9f  call    cs:__imp_CoTaskMemAlloc
0x180003fa6  nop     dword ptr [rax+rax+00h]
0x180003fab  mov     [rsi+40h], rax
0x180003faf  test    rax, rax
0x180003fb2  jz      loc_180003EDE
0x180003fb8  mov     rdx, [rbx+40h]
0x180003fbc  mov     rcx, rax; void *
0x180003fbf  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_ERROR@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_ERROR &,_EAP_ERROR const &)
0x180003fc4  mov     dil, al
0x180003fc7  test    al, al
0x180003fc9  jnz     short loc_180003FD5
0x180003fcb  mov     rcx, rsi; void *
0x180003fce  call    ??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z; Free<TaskAllocator>(tagEapHostPeerMethodResult &)
0x180003fd3  jmp     short loc_180003FFD
0x180003fd5  mov     eax, [rbx]
0x180003fd7  mov     [rsi], eax
0x180003fd9  mov     eax, [rbx+4]
0x180003fdc  mov     [rsi+4], eax
0x180003fdf  mov     eax, [rbx+8]
0x180003fe2  mov     [rsi+8], eax
0x180003fe5  mov     eax, [rbx+0Ch]
0x180003fe8  mov     [rsi+0Ch], eax
0x180003feb  mov     eax, [rbx+18h]
0x180003fee  mov     [rsi+18h], eax
0x180003ff1  mov     eax, [rbx+1Ch]
0x180003ff4  mov     [rsi+1Ch], eax
0x180003ff7  mov     eax, [rbx+30h]
0x180003ffa  mov     [rsi+30h], eax
0x180003ffd  mov     al, dil
0x180004000  mov     rbx, [rsp+28h+arg_0]
0x180004005  mov     rsi, [rsp+28h+arg_8]
0x18000400a  add     rsp, 20h
0x18000400e  pop     rdi
0x18000400f  retn
```
