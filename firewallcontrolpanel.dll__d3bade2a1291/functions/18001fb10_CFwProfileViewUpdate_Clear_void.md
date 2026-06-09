# CFwProfileViewUpdate::Clear(void)

- ea: `0x18001fb10`
- end: `0x18001fbc4`
- name: `?Clear@CFwProfileViewUpdate@@QEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(DirectUI::Element **this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x180016b98`

## callees

- `0x1800096a8`
- `0x18000994c`
- `0x18001fb10`

## import_xrefs

- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001fb25`
- `DUI70!?Remove@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001fb25`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fb6a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18001fb6a`

## pseudocode

```c
__int64 __fastcall CFwProfileViewUpdate::Clear(DirectUI::Element **this)
{
  int v2; // edi
  CFwCplLua *v3; // rcx
  __int64 v4; // rdx

  v2 = DirectUI::Element::Remove(this[3], this[4]);
  if ( v2 >= 0 )
  {
    v2 = DirectUI::Element::Destroy(this[4], 1);
    if ( v2 >= 0 )
    {
      CRefObject::Release(this[5]);
      this[5] = 0;
      this[3] = 0;
      this[4] = 0;
      return (unsigned int)v2;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 19;
      goto LABEL_5;
    }
  }
  else
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 18;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v3 + 2), v4, WPP_4a589502d135308541a166db9771a95e_Traceguids, (unsigned int)v2);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001fb10  mov     [rsp+arg_0], rbx
0x18001fb15  push    rdi
0x18001fb16  sub     rsp, 20h
0x18001fb1a  mov     rdx, [rcx+20h]
0x18001fb1e  mov     rbx, rcx
0x18001fb21  mov     rcx, [rcx+18h]
0x18001fb25  call    cs:__imp_?Remove@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Remove(DirectUI::Element *)
0x18001fb2b  mov     edi, eax
0x18001fb2d  test    eax, eax
0x18001fb2f  jns     short loc_18001FB64
0x18001fb31  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb38  lea     rax, WPP_GLOBAL_Control
0x18001fb3f  cmp     rcx, rax
0x18001fb42  jz      short loc_18001FBB7
0x18001fb44  test    byte ptr [rcx+1Ch], 1
0x18001fb48  jz      short loc_18001FBB7
0x18001fb4a  mov     edx, 12h
0x18001fb4f  mov     rcx, [rcx+10h]
0x18001fb53  lea     r8, WPP_4a589502d135308541a166db9771a95e_Traceguids
0x18001fb5a  mov     r9d, edi
0x18001fb5d  call    WPP_SF_d
0x18001fb62  jmp     short loc_18001FBB7
0x18001fb64  mov     rcx, [rbx+20h]
0x18001fb68  mov     dl, 1
0x18001fb6a  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18001fb70  mov     edi, eax
0x18001fb72  test    eax, eax
0x18001fb74  jns     short loc_18001FB96
0x18001fb76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb7d  lea     rax, WPP_GLOBAL_Control
0x18001fb84  cmp     rcx, rax
0x18001fb87  jz      short loc_18001FBB7
0x18001fb89  test    byte ptr [rcx+1Ch], 1
0x18001fb8d  jz      short loc_18001FBB7
0x18001fb8f  mov     edx, 13h
0x18001fb94  jmp     short loc_18001FB4F
0x18001fb96  mov     rcx, [rbx+28h]; this
0x18001fb9a  call    ?Release@CRefObject@@QEAAKXZ; CRefObject::Release(void)
0x18001fb9f  mov     qword ptr [rbx+28h], 0
0x18001fba7  mov     qword ptr [rbx+18h], 0
0x18001fbaf  mov     qword ptr [rbx+20h], 0
0x18001fbb7  mov     rbx, [rsp+28h+arg_0]
0x18001fbbc  mov     eax, edi
0x18001fbbe  add     rsp, 20h
0x18001fbc2  pop     rdi
0x18001fbc3  retn
```
