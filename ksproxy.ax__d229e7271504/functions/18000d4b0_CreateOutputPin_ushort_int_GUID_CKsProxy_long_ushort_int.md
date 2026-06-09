# CreateOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)

- ea: `0x18000d4b0`
- end: `0x18000d5ee`
- name: `?CreateOutputPin@@YAPEAVCBasePin@@PEAGHU_GUID@@PEAVCKsProxy@@PEAJ0H@Z`
- size: `318`
- prototype: `CKsOutputPin *__fastcall(unsigned __int16 *, unsigned int, struct _GUID *, struct CKsProxy *, int *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000b6fc`

## callees

- `0x180008690`
- `0x18000d4b0`
- `0x18001f1d0`
- `0x18001f620`
- `0x18002cac4`
- `0x1800304f4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000d522`
- `ADVAPI32!RegQueryValueExW` at `0x18000d522`

## pseudocode

```c
CKsOutputPin *__fastcall CreateOutputPin(
        unsigned __int16 *a1,
        unsigned int a2,
        struct _GUID *a3,
        struct CKsProxy *a4,
        int *a5,
        unsigned __int16 *a6,
        int a7)
{
  HKEY__ *m_DeviceRegKey; // rcx
  LSTATUS v10; // eax
  bool v11; // sf
  CKsOutputPin *v12; // rax
  unsigned __int16 *v13; // rdx
  struct _GUID *v14; // r9
  CKsOutputPin *v16; // rax
  unsigned __int16 *v17; // rdx
  struct _GUID *v18; // r9
  DWORD v19; // [rsp+40h] [rbp-30h] BYREF
  DWORD Type; // [rsp+44h] [rbp-2Ch] BYREF
  int v21; // [rsp+48h] [rbp-28h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h] BYREF

  v21 = 0;
  v19 = 16;
  m_DeviceRegKey = a4->m_DeviceRegKey;
  Type = 0;
  v22 = 0;
  v10 = RegQueryValueExW(m_DeviceRegKey, L"CustomVidProcHandler", 0, &Type, (LPBYTE)&v22, &v19);
  v11 = v10 < 0;
  if ( v10 )
  {
    if ( v10 > 0 )
      v11 = 1;
    if ( v11 )
    {
LABEL_5:
      v12 = (CKsOutputPin *)operator new(0x420u);
      if ( v12 )
        return CKsOutputPin::CKsOutputPin(v12, v13, a2, v14, a4, a5, a6, a7);
      return 0;
    }
  }
  else if ( v19 != 16 || Type != 3 )
  {
    goto LABEL_5;
  }
  if ( (int)IsPluginDisabled(a4->m_DeviceRegKey, &v21) >= 0 && v21 )
    goto LABEL_5;
  v16 = (CKsOutputPin *)operator new(0x4C8u);
  if ( v16 )
    return (CKsOutputPin *)CKsOutputPin2::CKsOutputPin2(v16, v17, a2, v18, a4, a5, a6, a7);
  return 0;
}

```

## disassembly

```asm
0x18000d4b0  mov     r11, rsp
0x18000d4b3  mov     [r11+8], rbx
0x18000d4b7  mov     [r11+18h], rsi
0x18000d4bb  push    rbp
0x18000d4bc  push    rdi
0x18000d4bd  push    r14
0x18000d4bf  mov     rbp, rsp
0x18000d4c2  sub     rsp, 70h
0x18000d4c6  mov     rax, cs:__security_cookie
0x18000d4cd  xor     rax, rsp
0x18000d4d0  mov     [rbp+var_10], rax
0x18000d4d4  mov     rsi, [rbp+arg_20]
0x18000d4d8  lea     rax, [rbp+var_30]
0x18000d4dc  mov     r14, [rbp+arg_28]
0x18000d4e0  mov     rbx, r9
0x18000d4e3  mov     [r11-60h], rax
0x18000d4e7  lea     r9, [rbp+Type]; lpType
0x18000d4eb  mov     edi, edx
0x18000d4ed  mov     [rbp+var_28], 0
0x18000d4f4  xorps   xmm0, xmm0
0x18000d4f7  mov     [rbp+var_30], 10h
0x18000d4fe  mov     rcx, [rbx+1F8h]; hKey
0x18000d505  lea     rax, [rbp+var_20]
0x18000d509  xor     r8d, r8d; lpReserved
0x18000d50c  mov     [rbp+Type], 0
0x18000d513  lea     rdx, aCustomvidproch; "CustomVidProcHandler"
0x18000d51a  mov     [r11-68h], rax
0x18000d51e  movups  [rbp+var_20], xmm0
0x18000d522  call    cs:__imp_RegQueryValueExW
0x18000d529  nop     dword ptr [rax+rax+00h]
0x18000d52e  test    eax, eax
0x18000d530  jz      short loc_18000D572
0x18000d532  jle     short loc_18000D53E
0x18000d534  movzx   eax, ax
0x18000d537  or      eax, 80070000h
0x18000d53c  test    eax, eax
0x18000d53e  jns     short loc_18000D57E
0x18000d540  mov     ecx, 420h; Size
0x18000d545  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d54a  test    rax, rax
0x18000d54d  jz      short loc_18000D5CA
0x18000d54f  mov     ecx, [rbp+arg_30]
0x18000d552  mov     r8d, edi; int
0x18000d555  mov     [rsp+70h+var_38], ecx; int
0x18000d559  mov     rcx, rax; this
0x18000d55c  mov     [rsp+70h+var_40], r14; unsigned __int16 *
0x18000d561  mov     [rsp+70h+var_48], rsi; int *
0x18000d566  mov     [rsp+70h+var_50], rbx; struct CKsProxy *
0x18000d56b  call    ??0CKsOutputPin@@QEAA@PEAGHU_GUID@@PEAVCKsProxy@@PEAJ0H@Z; CKsOutputPin::CKsOutputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)
0x18000d570  jmp     short loc_18000D5CC
0x18000d572  cmp     [rbp+var_30], 10h
0x18000d576  jnz     short loc_18000D540
0x18000d578  cmp     [rbp+Type], 3
0x18000d57c  jnz     short loc_18000D540
0x18000d57e  mov     rcx, [rbx+1F8h]; HKEY
0x18000d585  lea     rdx, [rbp+var_28]; int *
0x18000d589  call    ?IsPluginDisabled@@YAJPEAUHKEY__@@PEAH@Z; IsPluginDisabled(HKEY__ *,int *)
0x18000d58e  test    eax, eax
0x18000d590  js      short loc_18000D598
0x18000d592  cmp     [rbp+var_28], 0
0x18000d596  jnz     short loc_18000D540
0x18000d598  mov     ecx, 4C8h; Size
0x18000d59d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d5a2  test    rax, rax
0x18000d5a5  jz      short loc_18000D5CA
0x18000d5a7  mov     ecx, [rbp+arg_30]
0x18000d5aa  mov     r8d, edi; int
0x18000d5ad  mov     [rsp+70h+var_38], ecx; int
0x18000d5b1  mov     rcx, rax; this
0x18000d5b4  mov     [rsp+70h+var_40], r14; unsigned __int16 *
0x18000d5b9  mov     [rsp+70h+var_48], rsi; int *
0x18000d5be  mov     [rsp+70h+var_50], rbx; struct CKsProxy *
0x18000d5c3  call    ??0CKsOutputPin2@@QEAA@PEAGHU_GUID@@PEAVCKsProxy@@PEAJ0H@Z; CKsOutputPin2::CKsOutputPin2(ushort *,int,_GUID,CKsProxy *,long *,ushort *,int)
0x18000d5c8  jmp     short loc_18000D5CC
0x18000d5ca  xor     eax, eax
0x18000d5cc  mov     rcx, [rbp+var_10]
0x18000d5d0  xor     rcx, rsp; StackCookie
0x18000d5d3  call    __security_check_cookie
0x18000d5d8  lea     r11, [rsp+70h+var_s0]
0x18000d5dd  mov     rbx, [r11+20h]
0x18000d5e1  mov     rsi, [r11+30h]
0x18000d5e5  mov     rsp, r11
0x18000d5e8  pop     r14
0x18000d5ea  pop     rdi
0x18000d5eb  pop     rbp
0x18000d5ec  retn
```
