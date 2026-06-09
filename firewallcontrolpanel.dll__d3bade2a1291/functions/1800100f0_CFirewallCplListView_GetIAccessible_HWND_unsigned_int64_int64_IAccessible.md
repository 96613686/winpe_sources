# CFirewallCplListView::GetIAccessible(HWND__ *,unsigned __int64,__int64,IAccessible * *)

- ea: `0x1800100f0`
- end: `0x1800101e6`
- name: `?GetIAccessible@CFirewallCplListView@@AEAAJPEAUHWND__@@_K_JPEAPEAUIAccessible@@@Z`
- size: `246`
- prototype: `__int64 __usercall@<rax>(CFirewallCplListView *__hidden this@<rcx>, HWND@<rdx>, unsigned __int64@<r8>, __int64@<r9>, struct IAccessible **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fee0`

## callees

- `0x1800100f0`
- `0x1800257e0`
- `0x180032010`

## import_xrefs

- `OLEACC!CreateStdAccessibleProxyW` at `0x180010165`
- `OLEACC!CreateStdAccessibleProxyW` at `0x180010165`
- `OLEACC!ObjectFromLresult` at `0x18001013a`
- `OLEACC!ObjectFromLresult` at `0x18001013a`

## pseudocode

```c
HRESULT __fastcall CFirewallCplListView::GetIAccessible(
        CFirewallCplListView *this,
        HWND a2,
        WPARAM a3,
        LONG_PTR a4,
        struct IAccessible **a5)
{
  HRESULT result; // eax
  struct IAccessible *v8; // rbx
  struct DirectUI::DuiAccessible *v9; // rdi
  struct IAccessible *ppvObject; // [rsp+30h] [rbp-48h] BYREF
  struct DirectUI::DuiAccessible *v11; // [rsp+38h] [rbp-40h] BYREF
  struct IAccessible *v12; // [rsp+40h] [rbp-38h] BYREF

  v12 = 0;
  ppvObject = 0;
  v11 = 0;
  *a5 = 0;
  if ( ObjectFromLresult(a4, &IID_IAccessible, a3, (void **)&ppvObject) >= 0
    || (result = CreateStdAccessibleProxyW(a2, L"SysListView32", -4, &IID_IAccessible, (void **)&ppvObject), result >= 0) )
  {
    v8 = ppvObject;
    if ( (int)CListViewAccessible::Create(a2, *((struct IListViewAccDataSource **)this + 45), this, ppvObject, &v11) >= 0 )
    {
      v9 = v11;
      if ( (**(int (__fastcall ***)(struct DirectUI::DuiAccessible *, GUID *, struct IAccessible **))v11)(
             v11,
             &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
             &v12) >= 0 )
      {
        v8 = v12;
        ((void (__fastcall *)(struct IAccessible *))ppvObject->lpVtbl->Release)(ppvObject);
      }
      *((_QWORD *)this + 47) = v9;
    }
    *a5 = v8;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800100f0  mov     r11, rsp
0x1800100f3  push    rbx
0x1800100f4  push    rsi
0x1800100f5  push    rdi
0x1800100f6  push    r14
0x1800100f8  sub     rsp, 58h
0x1800100fc  mov     r14, [rsp+78h+arg_20]
0x180010104  mov     rax, r9
0x180010107  mov     rdi, rdx
0x18001010a  mov     qword ptr [r11-38h], 0
0x180010112  mov     rsi, rcx
0x180010115  mov     qword ptr [r11-48h], 0
0x18001011d  lea     r9, [r11-48h]; ppvObject
0x180010121  mov     qword ptr [r11-40h], 0
0x180010129  lea     rdx, IID_IAccessible; riid
0x180010130  mov     qword ptr [r14], 0
0x180010137  mov     rcx, rax; lResult
0x18001013a  call    cs:__imp_ObjectFromLresult
0x180010140  test    eax, eax
0x180010142  jns     short loc_18001016F
0x180010144  lea     rax, [rsp+78h+var_48]
0x180010149  mov     r8d, 0FFFFFFFCh; idObject
0x18001014f  lea     r9, IID_IAccessible; riid
0x180010156  mov     [rsp+78h+ppvObject], rax; ppvObject
0x18001015b  lea     rdx, pClassName; "SysListView32"
0x180010162  mov     rcx, rdi; hwnd
0x180010165  call    cs:__imp_CreateStdAccessibleProxyW
0x18001016b  test    eax, eax
0x18001016d  js      short loc_1800101DC
0x18001016f  mov     rbx, [rsp+78h+var_48]
0x180010174  lea     rax, [rsp+78h+var_40]
0x180010179  mov     rdx, [rsi+168h]; struct IListViewAccDataSource *
0x180010180  mov     r9, rbx; struct IAccessible *
0x180010183  mov     r8, rsi; struct DirectUI::Element *
0x180010186  mov     [rsp+78h+ppvObject], rax; struct DirectUI::DuiAccessible **
0x18001018b  mov     rcx, rdi; HWND
0x18001018e  call    ?Create@CListViewAccessible@@SAJPEAUHWND__@@PEAVIListViewAccDataSource@@PEAVElement@DirectUI@@PEAUIAccessible@@PEAPEAVDuiAccessible@5@@Z; CListViewAccessible::Create(HWND__ *,IListViewAccDataSource *,DirectUI::Element *,IAccessible *,DirectUI::DuiAccessible * *)
0x180010193  test    eax, eax
0x180010195  js      short loc_1800101D7
0x180010197  mov     rdi, [rsp+78h+var_40]
0x18001019c  lea     r8, [rsp+78h+var_38]
0x1800101a1  lea     rdx, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x1800101a8  mov     rcx, rdi
0x1800101ab  mov     rax, [rdi]
0x1800101ae  mov     rax, [rax]
0x1800101b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b6  test    eax, eax
0x1800101b8  js      short loc_1800101D0
0x1800101ba  mov     rcx, [rsp+78h+var_48]
0x1800101bf  mov     rbx, [rsp+78h+var_38]
0x1800101c4  mov     rax, [rcx]
0x1800101c7  mov     rax, [rax+10h]
0x1800101cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d0  mov     [rsi+178h], rdi
0x1800101d7  mov     [r14], rbx
0x1800101da  xor     eax, eax
0x1800101dc  add     rsp, 58h
0x1800101e0  pop     r14
0x1800101e2  pop     rdi
0x1800101e3  pop     rsi
0x1800101e4  pop     rbx
0x1800101e5  retn
```
