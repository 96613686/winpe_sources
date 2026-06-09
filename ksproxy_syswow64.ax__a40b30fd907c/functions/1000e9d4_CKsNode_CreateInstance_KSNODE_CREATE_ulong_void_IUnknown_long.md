# CKsNode::CreateInstance(KSNODE_CREATE *,ulong,void *,IUnknown *,long *)

- ea: `0x1000e9d4`
- end: `0x1000ea52`
- name: `?CreateInstance@CKsNode@@SGPAVCUnknown@@PAUKSNODE_CREATE@@KPAXPAUIUnknown@@PAJ@Z`
- size: `126`
- prototype: `struct CUnknown *__userpurge@<eax>(ACCESS_MASK@<edx>, struct $3E8BFD172CC0232DA5E7071EC2A0A89F *@<ecx>, struct KSNODE_CREATE *ParentHandle, struct IUnknown *, signed int *, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1000e900`

## callees

- `0x1000e9d4`
- `0x1002f736`
- `0x1003a6fd`

## import_xrefs

- `ksuser!KsCreateTopologyNode` at `0x1000ea19`
- `ksuser!KsCreateTopologyNode` at `0x1000ea19`

## pseudocode

```c
struct CUnknown *__userpurge CKsNode::CreateInstance@<eax>(
        ACCESS_MASK a1@<edx>,
        struct $3E8BFD172CC0232DA5E7071EC2A0A89F *a2@<ecx>,
        struct KSNODE_CREATE *ParentHandle,
        struct IUnknown *a4,
        signed int *a5,
        struct IUnknown *a6,
        int *a7)
{
  CUnknown *v8; // eax
  CUnknown *v9; // esi
  signed int TopologyNode; // eax
  signed int v11; // ecx
  const unsigned __int16 *v13; // [esp-4h] [ebp-10h]

  v8 = (CUnknown *)operator new(0x14u);
  v9 = v8;
  if ( v8 )
  {
    CUnknown::CUnknown(v8, v13, a4);
    v9->__vftable = (CUnknown_vtbl *)&CKsNode::`vftable'{for `CUnknown'};
    v9[1].__vftable = (CUnknown_vtbl *)&CKsNode::`vftable'{for `IKsControl'};
    v9[1].m_pUnknown = 0;
    TopologyNode = KsCreateTopologyNode(ParentHandle, a2, a1, (PHANDLE)&v9[1].m_pUnknown);
    v11 = (unsigned __int16)TopologyNode | 0x80070000;
    if ( TopologyNode <= 0 )
      v11 = TopologyNode;
    *a5 = v11;
    if ( v11 < 0 )
      v9[1].m_pUnknown = 0;
  }
  else
  {
    v9 = 0;
    *a5 = -2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x1000e9d4  mov     edi, edi
0x1000e9d6  push    ebp
0x1000e9d7  mov     ebp, esp
0x1000e9d9  push    ecx
0x1000e9da  push    ebx
0x1000e9db  push    esi
0x1000e9dc  push    14h; Size
0x1000e9de  mov     ebx, edx
0x1000e9e0  mov     [ebp+NodeCreate], ecx
0x1000e9e3  call    ??2@YAPAXI@Z; operator new(uint)
0x1000e9e8  mov     esi, eax
0x1000e9ea  pop     ecx
0x1000e9eb  test    esi, esi
0x1000e9ed  jz      short loc_1000EA3F
0x1000e9ef  push    edi
0x1000e9f0  push    [ebp+arg_4]; struct IUnknown *
0x1000e9f3  push    ecx; unsigned __int16 *
0x1000e9f4  mov     ecx, esi; this
0x1000e9f6  call    ??0CUnknown@@QAE@PBGPAUIUnknown@@@Z; CUnknown::CUnknown(ushort const *,IUnknown *)
0x1000e9fb  lea     edi, [esi+10h]
0x1000e9fe  mov     dword ptr [esi], offset ??_7CKsNode@@6BCUnknown@@@; const CKsNode::`vftable'{for `CUnknown'}
0x1000ea04  push    edi; NodeHandle
0x1000ea05  push    ebx; DesiredAccess
0x1000ea06  push    [ebp+NodeCreate]; NodeCreate
0x1000ea09  mov     dword ptr [esi+0Ch], offset ??_7CKsNode@@6BIKsControl@@@; const CKsNode::`vftable'{for `IKsControl'}
0x1000ea10  push    [ebp+ParentHandle]; ParentHandle
0x1000ea13  mov     dword ptr [edi], 0
0x1000ea19  call    ds:__imp__KsCreateTopologyNode@16; KsCreateTopologyNode(x,x,x,x)
0x1000ea1f  movzx   ecx, ax
0x1000ea22  or      ecx, 80070000h
0x1000ea28  test    eax, eax
0x1000ea2a  cmovle  ecx, eax
0x1000ea2d  mov     eax, [ebp+arg_8]
0x1000ea30  mov     [eax], ecx
0x1000ea32  test    ecx, ecx
0x1000ea34  jns     short loc_1000EA3C
0x1000ea36  mov     dword ptr [edi], 0
0x1000ea3c  pop     edi
0x1000ea3d  jmp     short loc_1000EA4A
0x1000ea3f  mov     ecx, [ebp+arg_8]
0x1000ea42  xor     esi, esi
0x1000ea44  mov     dword ptr [ecx], 8007000Eh
0x1000ea4a  mov     eax, esi
0x1000ea4c  pop     esi
0x1000ea4d  pop     ebx
0x1000ea4e  leave
0x1000ea4f  retn    0Ch
```
