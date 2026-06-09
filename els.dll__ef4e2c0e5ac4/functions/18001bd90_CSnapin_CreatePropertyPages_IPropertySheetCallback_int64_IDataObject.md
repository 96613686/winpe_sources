# CSnapin::CreatePropertyPages(IPropertySheetCallback *,__int64,IDataObject *)

- ea: `0x18001bd90`
- end: `0x18001be0e`
- name: `?CreatePropertyPages@CSnapin@@UEAAJPEAUIPropertySheetCallback@@_JPEAUIDataObject@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(CSnapin *this, struct IPropertySheetCallback *, __int64, struct IDataObject *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180014b88`
- `0x18001a2d0`
- `0x18001bd90`
- `0x18001d134`
- `0x18001f638`

## pseudocode

```c
__int64 __fastcall CSnapin::CreatePropertyPages(
        CSnapin *this,
        struct IPropertySheetCallback *a2,
        __int64 a3,
        struct IDataObject *a4)
{
  struct CDataObject *OwnDataObject; // rax
  struct _EVENTLOGRECORD *v8; // rax
  int v9; // r8d

  OwnDataObject = ExtractOwnDataObject(a4);
  if ( OwnDataObject && *((_DWORD *)OwnDataObject + 6) == 32769 && *((_DWORD *)OwnDataObject + 7) == 2 )
  {
    if ( !*((_DWORD *)this + 378) && !*((_QWORD *)this + 190) )
      return CSnapin::_CreatePropertyInspector((CSnapin *)((char *)this - 8), a2);
    v8 = CResultRecs::CopyRecord((CSnapin *)((char *)this + 80), *((_DWORD *)this + 394));
    CInspectorInfo::UpdateCurResultRec((CSnapin *)((char *)this + 1512), v8, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18001bd90  mov     [rsp+arg_0], rbx
0x18001bd95  mov     [rsp+arg_8], rsi
0x18001bd9a  push    rdi
0x18001bd9b  sub     rsp, 20h
0x18001bd9f  mov     rdi, rcx
0x18001bda2  mov     rsi, rdx
0x18001bda5  mov     rcx, r9; struct IDataObject *
0x18001bda8  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x18001bdad  test    rax, rax
0x18001bdb0  jz      short loc_18001BDFC
0x18001bdb2  cmp     dword ptr [rax+18h], 8001h
0x18001bdb9  jnz     short loc_18001BDFC
0x18001bdbb  cmp     dword ptr [rax+1Ch], 2
0x18001bdbf  jnz     short loc_18001BDFC
0x18001bdc1  lea     rbx, [rdi+5E8h]
0x18001bdc8  cmp     dword ptr [rbx], 0
0x18001bdcb  jnz     short loc_18001BDE2
0x18001bdcd  cmp     qword ptr [rbx+8], 0
0x18001bdd2  jnz     short loc_18001BDE2
0x18001bdd4  lea     rcx, [rdi-8]; this
0x18001bdd8  mov     rdx, rsi; struct IPropertySheetCallback *
0x18001bddb  call    ?_CreatePropertyInspector@CSnapin@@AEAAJPEAUIPropertySheetCallback@@@Z; CSnapin::_CreatePropertyInspector(IPropertySheetCallback *)
0x18001bde0  jmp     short loc_18001BDFE
0x18001bde2  mov     edx, [rdi+628h]; unsigned int
0x18001bde8  lea     rcx, [rdi+50h]; this
0x18001bdec  call    ?CopyRecord@CResultRecs@@QEAAPEAU_EVENTLOGRECORD@@K@Z; CResultRecs::CopyRecord(ulong)
0x18001bdf1  mov     rdx, rax; struct _EVENTLOGRECORD *
0x18001bdf4  mov     rcx, rbx; this
0x18001bdf7  call    ?UpdateCurResultRec@CInspectorInfo@@QEAAXPEAU_EVENTLOGRECORD@@H@Z; CInspectorInfo::UpdateCurResultRec(_EVENTLOGRECORD *,int)
0x18001bdfc  xor     eax, eax
0x18001bdfe  mov     rbx, [rsp+28h+arg_0]
0x18001be03  mov     rsi, [rsp+28h+arg_8]
0x18001be08  add     rsp, 20h
0x18001be0c  pop     rdi
0x18001be0d  retn
```
