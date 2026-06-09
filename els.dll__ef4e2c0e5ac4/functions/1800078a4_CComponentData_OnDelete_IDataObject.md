# CComponentData::_OnDelete(IDataObject *)

- ea: `0x1800078a4`
- end: `0x18000798a`
- name: `?_OnDelete@CComponentData@@AEAAJPEAUIDataObject@@@Z`
- size: `230`
- prototype: `int(CComponentData *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800065d0`

## callees

- `0x180004f68`
- `0x180006cc0`
- `0x1800078a4`
- `0x18001c48c`
- `0x18001f638`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::_OnDelete(CComponentData *this, struct IDataObject *a2)
{
  struct CDataObject *OwnDataObject; // rax
  __int64 v4; // rbx
  __int64 v6; // rcx
  int v7; // esi
  CSnapin *i; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax

  OwnDataObject = ExtractOwnDataObject(a2);
  if ( !OwnDataObject || !*((_DWORD *)OwnDataObject + 7) )
    return 0;
  v4 = *((_QWORD *)OwnDataObject + 2);
  if ( (*(_WORD *)(v4 + 24) & 0x100) == 0 )
    return 2147942487LL;
  v6 = *((_QWORD *)this + 145);
  v7 = 0;
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v6 + 32LL))(v6, *(_QWORD *)(v4 + 4856), 1);
    if ( v7 >= 0 )
    {
      for ( i = (CSnapin *)*((_QWORD *)this + 8);
            i;
            i = (CSnapin *)((*((_QWORD *)i + 8) - 56LL) & -(__int64)(*((_QWORD *)i + 8) != 0)) )
      {
        CSnapin::HandleLogDeletion(i, (struct CLogInfo *)v4);
      }
      v9 = *(_QWORD *)(v4 + 4864);
      if ( v9 )
      {
        v10 = *(_QWORD *)(v9 + 136);
        if ( v10 )
        {
          if ( v10 == v4 )
            *(_QWORD *)(v9 + 136) = *(_QWORD *)(v4 + 8);
          CDLink::UnLink((CDLink *)v4);
        }
      }
      CLogInfo::Release((CLogInfo *)v4);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800078a4  mov     [rsp+arg_0], rbx
0x1800078a9  mov     [rsp+arg_8], rsi
0x1800078ae  push    rdi
0x1800078af  sub     rsp, 20h
0x1800078b3  mov     rdi, rcx
0x1800078b6  mov     rcx, rdx; struct IDataObject *
0x1800078b9  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x1800078be  test    rax, rax
0x1800078c1  jz      loc_180007978
0x1800078c7  cmp     dword ptr [rax+1Ch], 0
0x1800078cb  jz      loc_180007978
0x1800078d1  mov     rbx, [rax+10h]
0x1800078d5  mov     eax, 100h
0x1800078da  test    [rbx+18h], ax
0x1800078de  jnz     short loc_1800078EA
0x1800078e0  mov     eax, 80070057h
0x1800078e5  jmp     loc_18000797A
0x1800078ea  mov     rcx, [rdi+488h]
0x1800078f1  xor     esi, esi
0x1800078f3  test    rcx, rcx
0x1800078f6  jz      short loc_180007974
0x1800078f8  mov     rax, [rcx]
0x1800078fb  lea     r8d, [rsi+1]
0x1800078ff  mov     rdx, [rbx+12F8h]
0x180007906  mov     rax, [rax+20h]
0x18000790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000790f  mov     esi, eax
0x180007911  test    eax, eax
0x180007913  js      short loc_180007974
0x180007915  mov     rdi, [rdi+40h]
0x180007919  test    rdi, rdi
0x18000791c  jz      short loc_18000793C
0x18000791e  mov     rdx, rbx; struct CLogInfo *
0x180007921  mov     rcx, rdi; this
0x180007924  call    ?HandleLogDeletion@CSnapin@@QEAAXPEAVCLogInfo@@@Z; CSnapin::HandleLogDeletion(CLogInfo *)
0x180007929  mov     rcx, [rdi+40h]
0x18000792d  lea     rax, [rcx-38h]
0x180007931  neg     rcx
0x180007934  sbb     rdi, rdi
0x180007937  and     rdi, rax
0x18000793a  jnz     short loc_18000791E
0x18000793c  mov     rcx, [rbx+1300h]
0x180007943  test    rcx, rcx
0x180007946  jz      short loc_18000796C
0x180007948  mov     rax, [rcx+88h]
0x18000794f  test    rax, rax
0x180007952  jz      short loc_18000796C
0x180007954  cmp     rax, rbx
0x180007957  jnz     short loc_180007964
0x180007959  mov     rax, [rbx+8]
0x18000795d  mov     [rcx+88h], rax
0x180007964  mov     rcx, rbx; this
0x180007967  call    ?UnLink@CDLink@@QEAAXXZ; CDLink::UnLink(void)
0x18000796c  mov     rcx, rbx; this
0x18000796f  call    ?Release@CLogInfo@@QEAAKXZ; CLogInfo::Release(void)
0x180007974  mov     eax, esi
0x180007976  jmp     short loc_18000797A
0x180007978  xor     eax, eax
0x18000797a  mov     rbx, [rsp+28h+arg_0]
0x18000797f  mov     rsi, [rsp+28h+arg_8]
0x180007984  add     rsp, 20h
0x180007988  pop     rdi
0x180007989  retn
```
