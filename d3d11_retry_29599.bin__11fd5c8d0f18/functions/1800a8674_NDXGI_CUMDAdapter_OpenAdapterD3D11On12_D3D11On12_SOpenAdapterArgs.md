# NDXGI::CUMDAdapter::OpenAdapterD3D11On12(D3D11On12::SOpenAdapterArgs &)

- ea: `0x1800a8674`
- end: `0x1800a8703`
- name: `?OpenAdapterD3D11On12@CUMDAdapter@NDXGI@@QEAAJAEAUSOpenAdapterArgs@D3D11On12@@@Z`
- size: `143`
- prototype: `int(NDXGI::CUMDAdapter *__hidden this, struct D3D11On12::SOpenAdapterArgs *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18006a958`
- `0x1800a5d80`

## callees

- `0x1800229a0`
- `0x1800a8674`
- `0x1800a870c`

## import_xrefs

- `d3d11on12!OpenAdapter_D3D11On12` at `0x1800a86b1`
- `d3d11on12!OpenAdapter_D3D11On12` at `0x1800a86b1`

## string_xrefs

- `0x1800a86c2`: `OpenAdapter_D3D11On12`

## pseudocode

```c
__int64 __fastcall NDXGI::CUMDAdapter::OpenAdapterD3D11On12(
        NDXGI::CUMDAdapter *this,
        struct D3D11On12::SOpenAdapterArgs *a2)
{
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // r9
  unsigned int v7; // ebx
  _OWORD v9[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+50h] [rbp-18h]

  memset(v9, 0, sizeof(v9));
  v10 = 0;
  NDXGI::CUMDAdapter::Fill11On12OpenAdapterStructs(this, (struct D3D10DDIARG_OPENADAPTER *)v9, a2);
  v5 = OpenAdapter_D3D11On12(v9, v4);
  v7 = v5;
  if ( v5 >= 0 )
  {
    *((_QWORD *)this + 113) = *((_QWORD *)&v9[0] + 1);
    *((_DWORD *)this + 232) = *((_DWORD *)a2 + 13);
  }
  else
  {
    CModule::RecordJournal((CModule *)&g_Module, v5, "OpenAdapter_D3D11On12", v6, 1);
  }
  *((_DWORD *)this + 9) = v7;
  return v7;
}

```

## disassembly

```asm
0x1800a8674  mov     r11, rsp
0x1800a8677  mov     [r11+8], rbx
0x1800a867b  mov     [r11+10h], rsi
0x1800a867f  push    rdi
0x1800a8680  sub     rsp, 60h
0x1800a8684  mov     rsi, rdx
0x1800a8687  mov     rdi, rcx
0x1800a868a  xorps   xmm0, xmm0
0x1800a868d  xor     eax, eax
0x1800a868f  movups  [rsp+68h+var_38], xmm0
0x1800a8694  movups  [rsp+68h+var_28], xmm0
0x1800a8699  mov     [r11-18h], rax
0x1800a869d  mov     r8, rdx; struct D3D11On12::SOpenAdapterArgs *
0x1800a86a0  lea     rdx, [r11-38h]; struct D3D10DDIARG_OPENADAPTER *
0x1800a86a4  call    ?Fill11On12OpenAdapterStructs@CUMDAdapter@NDXGI@@IEAAXPEAUD3D10DDIARG_OPENADAPTER@@PEAUSOpenAdapterArgs@D3D11On12@@@Z; NDXGI::CUMDAdapter::Fill11On12OpenAdapterStructs(D3D10DDIARG_OPENADAPTER *,D3D11On12::SOpenAdapterArgs *)
0x1800a86a9  mov     rdx, r8
0x1800a86ac  lea     rcx, [rsp+68h+var_38]
0x1800a86b1  call    cs:__imp_OpenAdapter_D3D11On12
0x1800a86b7  mov     ebx, eax
0x1800a86b9  test    eax, eax
0x1800a86bb  jns     short loc_1800A86D9
0x1800a86bd  mov     [rsp+68h+var_48], 1; bool
0x1800a86c2  lea     r8, aOpenadapterD3d_0; "OpenAdapter_D3D11On12"
0x1800a86c9  mov     edx, eax; unsigned int
0x1800a86cb  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800a86d2  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800a86d7  jmp     short loc_1800A86EE
0x1800a86d9  mov     rax, qword ptr [rsp+68h+var_38+8]
0x1800a86de  mov     [rdi+388h], rax
0x1800a86e5  mov     eax, [rsi+34h]
0x1800a86e8  mov     [rdi+3A0h], eax
0x1800a86ee  mov     [rdi+24h], ebx
0x1800a86f1  mov     eax, ebx
0x1800a86f3  mov     rbx, [rsp+68h+arg_0]
0x1800a86f8  mov     rsi, [rsp+68h+arg_8]
0x1800a86fd  add     rsp, 60h
0x1800a8701  pop     rdi
0x1800a8702  retn
```
