# CKsNode::CreateInstance(KSNODE_CREATE *,ulong,void *,IUnknown *,long *)

- ea: `0x18001d2e4`
- end: `0x18001d39c`
- name: `?CreateInstance@CKsNode@@SAPEAVCUnknown@@PEAUKSNODE_CREATE@@KPEAXPEAUIUnknown@@PEAJ@Z`
- size: `184`
- prototype: `struct IUnknown *__fastcall(PKSNODE_CREATE NodeCreate, ACCESS_MASK DesiredAccess, HANDLE ParentHandle, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021780`

## callees

- `0x18001d2e4`
- `0x18001f1d0`

## import_xrefs

- `ksuser!KsCreateTopologyNode` at `0x18001d351`
- `ksuser!KsCreateTopologyNode` at `0x18001d351`

## pseudocode

```c
struct IUnknown *__fastcall CKsNode::CreateInstance(
        PKSNODE_CREATE NodeCreate,
        ACCESS_MASK DesiredAccess,
        HANDLE ParentHandle,
        struct IUnknown *a4,
        int *a5)
{
  struct IUnknown *v9; // rax
  struct IUnknown *v10; // rbx
  signed int TopologyNode; // eax
  signed int v12; // ecx

  v9 = (struct IUnknown *)operator new(0x28u);
  v10 = v9;
  if ( v9 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    if ( a4 )
      v9 = a4;
    v10[1].__vftable = (IUnknown_vtbl *)v9;
    LODWORD(v10[2].__vftable) = 0;
    v10->__vftable = (IUnknown_vtbl *)&CKsNode::`vftable'{for `CUnknown'};
    v10[3].__vftable = (IUnknown_vtbl *)&CKsNode::`vftable'{for `IKsControl'};
    v10[4].__vftable = 0;
    TopologyNode = KsCreateTopologyNode(ParentHandle, NodeCreate, DesiredAccess, (PHANDLE)&v10[4].__vftable);
    v12 = TopologyNode;
    if ( TopologyNode > 0 )
      v12 = (unsigned __int16)TopologyNode | 0x80070000;
    *a5 = v12;
    if ( v12 < 0 )
      v10[4].__vftable = 0;
  }
  else
  {
    v10 = 0;
    *a5 = -2147024882;
  }
  return v10;
}

```

## disassembly

```asm
0x18001d2e4  push    rbx
0x18001d2e6  push    rbp
0x18001d2e7  push    rsi
0x18001d2e8  push    rdi
0x18001d2e9  push    r14
0x18001d2eb  sub     rsp, 20h
0x18001d2ef  mov     r14, rcx
0x18001d2f2  mov     rdi, r9
0x18001d2f5  mov     ecx, 28h ; '('; Size
0x18001d2fa  mov     rsi, r8
0x18001d2fd  mov     ebp, edx
0x18001d2ff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d304  mov     rbx, rax
0x18001d307  test    rax, rax
0x18001d30a  jz      short loc_18001D380
0x18001d30c  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001d313  test    rdi, rdi
0x18001d316  mov     r8d, ebp; DesiredAccess
0x18001d319  mov     rdx, r14; NodeCreate
0x18001d31c  mov     rcx, rsi; ParentHandle
0x18001d31f  cmovnz  rax, rdi
0x18001d323  lea     rdi, [rbx+20h]
0x18001d327  mov     [rbx+8], rax
0x18001d32b  mov     r9, rdi; NodeHandle
0x18001d32e  lea     rax, ??_7CKsNode@@6BCUnknown@@@; const CKsNode::`vftable'{for `CUnknown'}
0x18001d335  mov     dword ptr [rbx+10h], 0
0x18001d33c  mov     [rbx], rax
0x18001d33f  lea     rax, ??_7CKsNode@@6BIKsControl@@@; const CKsNode::`vftable'{for `IKsControl'}
0x18001d346  mov     [rbx+18h], rax
0x18001d34a  mov     qword ptr [rdi], 0
0x18001d351  call    cs:__imp_KsCreateTopologyNode
0x18001d358  nop     dword ptr [rax+rax+00h]
0x18001d35d  mov     ecx, eax
0x18001d35f  test    eax, eax
0x18001d361  jle     short loc_18001D36C
0x18001d363  movzx   ecx, ax
0x18001d366  or      ecx, 80070000h
0x18001d36c  mov     rax, [rsp+48h+arg_20]
0x18001d371  mov     [rax], ecx
0x18001d373  test    ecx, ecx
0x18001d375  jns     short loc_18001D38D
0x18001d377  mov     qword ptr [rdi], 0
0x18001d37e  jmp     short loc_18001D38D
0x18001d380  mov     rax, [rsp+48h+arg_20]
0x18001d385  xor     ebx, ebx
0x18001d387  mov     dword ptr [rax], 8007000Eh
0x18001d38d  mov     rax, rbx
0x18001d390  add     rsp, 20h
0x18001d394  pop     r14
0x18001d396  pop     rdi
0x18001d397  pop     rsi
0x18001d398  pop     rbp
0x18001d399  pop     rbx
0x18001d39a  retn
```
