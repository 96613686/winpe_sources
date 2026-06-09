# Smb2ShouldFetchInformationFromDirCache

- ea: `0x140019be0`
- end: `0x140019d52`
- name: `Smb2ShouldFetchInformationFromDirCache`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140019be0`
- `0x14002ed54`

## import_xrefs

- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140019c92`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140019c92`

## pseudocode

```c
bool __fastcall Smb2ShouldFetchInformationFromDirCache(__int64 a1, int a2)
{
  int v2; // eax
  char v4; // cl
  bool v6; // al
  bool v7; // si
  __int64 *v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx

  v2 = *(_DWORD *)(a1 + 120);
  v4 = *(_BYTE *)(a1 + 32);
  v6 = (v2 & 0x10000000) == 0;
  if ( v4 )
  {
    if ( v4 == 12 )
    {
      v7 = v6;
      if ( *(_BYTE *)(a1 + 33) != 1 )
        v7 = 0;
    }
    else
    {
      v7 = 0;
    }
  }
  else
  {
    v7 = v6;
  }
  if ( a2 != 79 && a2 != 12 )
  {
    switch ( a2 )
    {
      case 1:
      case 2:
      case 3:
      case 37:
      case 38:
      case 60:
      case 63:
      case 78:
      case 80:
      case 81:
        break;
      default:
        return 0;
    }
  }
  v8 = *(__int64 **)(a1 + 56);
  if ( v8[3] >= 104857600 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids, v8 + 45);
    }
    return 0;
  }
  v9 = v8[17];
  if ( (*(_DWORD *)(v9 + 56) & 0x400) != 0 )
    return 0;
  v10 = *(_QWORD *)(v8[15] + 32);
  if ( (*(_DWORD *)(v10 + 96) & 0x80u) != 0
    || (*(_BYTE *)(*(_QWORD *)(v10 + 32) + 764LL) & 8) == 0
    || (*(_DWORD *)(v9 + 8) & 1) != 0
    || (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL) + 424LL) + 184LL) & 0x800000) != 0
    || !*(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(a1 + 80)) + 20) )
  {
    return 0;
  }
  if ( (a2 == 60 || a2 == 63) && (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1314LL) & 4) == 0 )
    return 0;
  return v7 && dbgShouldCacheDirInformation;
}

```

## disassembly

```asm
0x140019be0  mov     [rsp+arg_0], rbx
0x140019be5  mov     [rsp+arg_8], rsi
0x140019bea  push    rdi
0x140019beb  sub     rsp, 20h
0x140019bef  mov     eax, [rcx+78h]
0x140019bf2  mov     rbx, rcx
0x140019bf5  movzx   ecx, byte ptr [rcx+20h]
0x140019bf9  mov     edi, edx
0x140019bfb  shr     eax, 1Ch
0x140019bfe  not     al
0x140019c00  and     al, 1
0x140019c02  test    cl, cl
0x140019c04  jz      loc_140019CEB
0x140019c0a  cmp     cl, 0Ch
0x140019c0d  jnz     loc_140019CF3
0x140019c13  movzx   esi, al
0x140019c16  xor     eax, eax
0x140019c18  cmp     byte ptr [rbx+21h], 1
0x140019c1c  cmovnz  esi, eax
0x140019c1f  cmp     edi, 4Fh ; 'O'
0x140019c22  jnz     loc_140019CDD
0x140019c28  mov     rdx, [rbx+38h]; jumptable 000000014003B931 cases 1-3,37,38,60,63,78,80,81
0x140019c2c  cmp     qword ptr [rdx+18h], 6400000h
0x140019c34  jge     loc_140019CFB
0x140019c3a  mov     r8, [rdx+88h]
0x140019c41  test    dword ptr [r8+38h], 400h
0x140019c49  jnz     short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019c4b  mov     rax, [rdx+78h]
0x140019c4f  mov     rcx, [rax+20h]
0x140019c53  mov     eax, [rcx+60h]
0x140019c56  test    al, al
0x140019c58  js      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019c5a  mov     rax, [rcx+20h]
0x140019c5e  test    byte ptr [rax+2FCh], 8
0x140019c65  jz      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019c67  mov     eax, [r8+8]
0x140019c6b  test    al, 1
0x140019c6d  jnz     short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019c6f  mov     rax, [rbx+48h]
0x140019c73  mov     rcx, [rax+28h]
0x140019c77  mov     rax, [rcx+28h]
0x140019c7b  mov     rcx, [rax+1A8h]
0x140019c82  test    dword ptr [rcx+0B8h], 800000h
0x140019c8c  jnz     short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019c8e  mov     rcx, [rbx+50h]
0x140019c92  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140019c99  nop     dword ptr [rax+rax+00h]
0x140019c9e  cmp     dword ptr [rax+14h], 0
0x140019ca2  jz      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019ca4  cmp     edi, 3Ch ; '<'
0x140019ca7  jz      loc_140019D39
0x140019cad  cmp     edi, 3Fh ; '?'
0x140019cb0  jz      loc_140019D39
0x140019cb6  test    sil, sil
0x140019cb9  jz      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019cbb  movzx   eax, cs:dbgShouldCacheDirInformation
0x140019cc2  test    al, al
0x140019cc4  jnz     loc_140019D4B
0x140019cca  xor     al, al; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019ccc  mov     rbx, [rsp+28h+arg_0]
0x140019cd1  mov     rsi, [rsp+28h+arg_8]
0x140019cd6  add     rsp, 20h
0x140019cda  pop     rdi
0x140019cdb  retn
0x140019cdd  cmp     edi, 0Ch
0x140019ce0  jz      loc_140019C28; jumptable 000000014003B931 cases 1-3,37,38,60,63,78,80,81
0x140019ce6  jmp     loc_14003B90C
0x140019ceb  movzx   esi, al
0x140019cee  jmp     loc_140019C1F
0x140019cf3  xor     sil, sil
0x140019cf6  jmp     loc_140019C1F
0x140019cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d02  lea     rax, WPP_GLOBAL_Control
0x140019d09  cmp     rcx, rax
0x140019d0c  jz      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019d0e  mov     eax, [rcx+2Ch]
0x140019d11  test    al, al
0x140019d13  jns     short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019d15  cmp     byte ptr [rcx+29h], 1
0x140019d19  jb      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019d1b  mov     rcx, [rcx+18h]
0x140019d1f  lea     r9, [rdx+168h]
0x140019d26  mov     edx, 0Eh
0x140019d2b  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140019d32  call    WPP_SF_Z
0x140019d37  jmp     short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019d39  mov     rax, [rbx+50h]
0x140019d3d  test    byte ptr [rax+522h], 4
0x140019d44  jz      short def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x140019d46  jmp     loc_140019CB6
0x140019d4b  mov     al, 1
0x140019d4d  jmp     loc_140019CCC
0x14003b90c  lea     eax, [rdx-1]; switch 81 cases
0x14003b90f  cmp     eax, 50h
0x14003b912  ja      def_14003B931; jumptable 000000014003B931 default case, cases 4-36,39-59,61,62,64-77,79
0x14003b918  lea     rdx, cs:140000000h
0x14003b91f  movzx   eax, ds:(byte_14003FECE - 140000000h)[rdx+rax]
0x14003b927  mov     ecx, ds:(jpt_14003B931 - 140000000h)[rdx+rax*4]
0x14003b92e  add     rcx, rdx
0x14003b931  jmp     rcx; switch jump
```
