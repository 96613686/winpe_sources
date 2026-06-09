# Copy<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &,_EAP_INTERACTIVE_UI_DATA const &)

- ea: `0x18000caec`
- end: `0x18000cbbc`
- name: `??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_INTERACTIVE_UI_DATA@@AEBU0@@Z`
- size: `208`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000e5e0`

## callees

- `0x18000c964`
- `0x18000caec`
- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cb6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Copy<TaskAllocator>(__int64 a1, __int64 a2)
{
  char v4; // bl
  int v5; // eax
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  LPVOID v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  LPVOID v13; // rax
  LPVOID v14; // rbp
  __int64 v16; // rsi

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)a1 = *(_DWORD *)a2;
  v4 = 1;
  v5 = *(_DWORD *)(a2 + 4);
  if ( v5 )
  {
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)(a1 + 8) = *(_DWORD *)(a2 + 8);
    *(_DWORD *)(a1 + 12) = *(_DWORD *)(a2 + 12);
    if ( *(_DWORD *)(a2 + 12) )
    {
      v6 = *(_DWORD *)(a2 + 8);
      if ( !v6 )
        goto LABEL_8;
      v7 = v6 - 1;
      if ( !v7 )
        goto LABEL_8;
      v8 = v7 - 1;
      if ( !v8 || (v9 = v8 - 1) == 0 )
      {
        v13 = CoTaskMemAlloc(0x20u);
        *(_QWORD *)(a1 + 16) = v13;
        v14 = v13;
        if ( v13 )
        {
          v16 = *(_QWORD *)(a2 + 16);
          v4 = Copy<TaskAllocator>((__int64)v13, v16);
          if ( v4 )
          {
            v11 = v16 + 16;
            v12 = (__int64)v14 + 16;
LABEL_16:
            v4 = Copy<TaskAllocator>(v12, v11);
            if ( v4 )
              return v4;
          }
LABEL_12:
          Free<TaskAllocator>(a1);
          return v4;
        }
LABEL_11:
        v4 = 0;
        goto LABEL_12;
      }
      if ( (unsigned int)(v9 - 1) <= 1 )
      {
LABEL_8:
        v10 = CoTaskMemAlloc(0x10u);
        *(_QWORD *)(a1 + 16) = v10;
        if ( v10 )
        {
          v11 = *(_QWORD *)(a2 + 16);
          v12 = (__int64)v10;
          goto LABEL_16;
        }
        goto LABEL_11;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000caec  push    rbx
0x18000caee  push    rbp
0x18000caef  push    rsi
0x18000caf0  push    rdi
0x18000caf1  sub     rsp, 28h
0x18000caf5  xor     eax, eax
0x18000caf7  xorps   xmm0, xmm0
0x18000cafa  movups  xmmword ptr [rcx], xmm0
0x18000cafd  mov     [rcx+10h], rax
0x18000cb01  mov     rsi, rdx
0x18000cb04  mov     eax, [rdx]
0x18000cb06  mov     rdi, rcx
0x18000cb09  mov     [rcx], eax
0x18000cb0b  mov     bl, 1
0x18000cb0d  mov     eax, [rdx+4]
0x18000cb10  test    eax, eax
0x18000cb12  jz      short loc_18000CB87
0x18000cb14  mov     [rcx+4], eax
0x18000cb17  mov     eax, [rdx+8]
0x18000cb1a  mov     [rcx+8], eax
0x18000cb1d  mov     eax, [rdx+0Ch]
0x18000cb20  mov     [rcx+0Ch], eax
0x18000cb23  cmp     dword ptr [rdx+0Ch], 0
0x18000cb27  jz      short loc_18000CB87
0x18000cb29  mov     ecx, [rdx+8]
0x18000cb2c  test    ecx, ecx
0x18000cb2e  jz      short loc_18000CB49
0x18000cb30  sub     ecx, 1
0x18000cb33  jz      short loc_18000CB49
0x18000cb35  sub     ecx, 1
0x18000cb38  jz      short loc_18000CB66
0x18000cb3a  sub     ecx, 1
0x18000cb3d  jz      short loc_18000CB66
0x18000cb3f  sub     ecx, 1
0x18000cb42  jz      short loc_18000CB49
0x18000cb44  cmp     ecx, 1
0x18000cb47  jnz     short loc_18000CB87
0x18000cb49  mov     ecx, 10h; cb
0x18000cb4e  call    cs:__imp_CoTaskMemAlloc
0x18000cb54  mov     [rdi+10h], rax
0x18000cb58  test    rax, rax
0x18000cb5b  jz      short loc_18000CB7D
0x18000cb5d  mov     rdx, [rsi+10h]
0x18000cb61  mov     rcx, rax
0x18000cb64  jmp     short loc_18000CBAF
0x18000cb66  mov     ecx, 20h ; ' '; cb
0x18000cb6b  call    cs:__imp_CoTaskMemAlloc
0x18000cb71  mov     [rdi+10h], rax
0x18000cb75  mov     rbp, rax
0x18000cb78  test    rax, rax
0x18000cb7b  jnz     short loc_18000CB92
0x18000cb7d  xor     bl, bl
0x18000cb7f  mov     rcx, rdi
0x18000cb82  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18000cb87  mov     al, bl
0x18000cb89  add     rsp, 28h
0x18000cb8d  pop     rdi
0x18000cb8e  pop     rsi
0x18000cb8f  pop     rbp
0x18000cb90  pop     rbx
0x18000cb91  retn
0x18000cb92  mov     rsi, [rsi+10h]
0x18000cb96  mov     rcx, rbp
0x18000cb99  mov     rdx, rsi
0x18000cb9c  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &,_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18000cba1  mov     bl, al
0x18000cba3  test    al, al
0x18000cba5  jz      short loc_18000CB7F
0x18000cba7  lea     rdx, [rsi+10h]
0x18000cbab  lea     rcx, [rbp+10h]
0x18000cbaf  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &,_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18000cbb4  mov     bl, al
0x18000cbb6  test    al, al
0x18000cbb8  jz      short loc_18000CB7F
0x18000cbba  jmp     short loc_18000CB87
```
