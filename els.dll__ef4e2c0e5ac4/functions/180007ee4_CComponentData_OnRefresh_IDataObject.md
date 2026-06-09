# CComponentData::_OnRefresh(IDataObject *)

- ea: `0x180007ee4`
- end: `0x180007f69`
- name: `?_OnRefresh@CComponentData@@AEAAJPEAUIDataObject@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x1800018a0`
- `0x1800066dc`
- `0x180007ee4`
- `0x180016ffc`
- `0x18001f638`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::_OnRefresh(CComponentData *this, struct IDataObject *a2)
{
  struct CDataObject *OwnDataObject; // rax
  bool v4; // zf
  CLogInfo *v6; // [rsp+40h] [rbp+18h] BYREF

  OwnDataObject = ExtractOwnDataObject(a2);
  if ( OwnDataObject )
  {
    v4 = *((_DWORD *)OwnDataObject + 7) == 1;
    v6 = 0;
    if ( v4 )
      v6 = (CLogInfo *)*((_QWORD *)OwnDataObject + 2);
    else
      (*(void (__fastcall **)(__int64, CLogInfo **))(*(_QWORD *)(*((_QWORD *)this + 9) + 40LL) + 40LL))(
        *((_QWORD *)this + 9) + 40LL,
        &v6);
    CLruCache::Clear((CLruCache *)&g_SidCache);
    CLruCache::Clear((CLruCache *)&g_DllCache);
    CLogInfo::Refresh(v6);
    CComponentData::NotifySnapinsLogChanged(this, 0, (__int64)v6, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180007ee4  push    rbx
0x180007ee6  sub     rsp, 20h
0x180007eea  mov     rbx, rcx
0x180007eed  mov     rcx, rdx; struct IDataObject *
0x180007ef0  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x180007ef5  test    rax, rax
0x180007ef8  jz      short loc_180007F61
0x180007efa  cmp     dword ptr [rax+1Ch], 1
0x180007efe  mov     [rsp+28h+arg_10], 0
0x180007f07  jnz     short loc_180007F14
0x180007f09  mov     rax, [rax+10h]
0x180007f0d  mov     [rsp+28h+arg_10], rax
0x180007f12  jmp     short loc_180007F2D
0x180007f14  mov     rcx, [rbx+48h]
0x180007f18  lea     rdx, [rsp+28h+arg_10]
0x180007f1d  add     rcx, 28h ; '('
0x180007f21  mov     rax, [rcx]
0x180007f24  mov     rax, [rax+28h]
0x180007f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f2d  lea     rcx, ?g_SidCache@@3VCSidCache@@A; this
0x180007f34  call    ?Clear@CLruCache@@UEAAXXZ; CLruCache::Clear(void)
0x180007f39  lea     rcx, ?g_DllCache@@3VCDllCache@@A; this
0x180007f40  call    ?Clear@CLruCache@@UEAAXXZ; CLruCache::Clear(void)
0x180007f45  mov     rcx, [rsp+28h+arg_10]; this
0x180007f4a  call    ?Refresh@CLogInfo@@QEAAXXZ; CLogInfo::Refresh(void)
0x180007f4f  mov     r8, [rsp+28h+arg_10]; __int64
0x180007f54  xor     r9d, r9d; int
0x180007f57  xor     edx, edx; unsigned __int64
0x180007f59  mov     rcx, rbx; this
0x180007f5c  call    ?NotifySnapinsLogChanged@CComponentData@@QEAAH_K_JH@Z; CComponentData::NotifySnapinsLogChanged(unsigned __int64,__int64,int)
0x180007f61  xor     eax, eax
0x180007f63  add     rsp, 20h
0x180007f67  pop     rbx
0x180007f68  retn
```
