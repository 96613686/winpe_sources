# ListView_OnNCDestroy

- ea: `0x180057658`
- end: `0x180057792`
- name: `ListView_OnNCDestroy`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18005c0a0`

## callees

- `0x18002ec60`
- `0x18002ece0`
- `0x180057658`
- `0x18005b198`
- `0x180085890`
- `0x180090020`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005770d`
- `GDI32!DeleteObject` at `0x18005770d`
- `KERNEL32!LocalFree` at `0x18005776a`
- `KERNEL32!LocalFree` at `0x18005776a`
- `KERNEL32!LocalFree` at `0x18005778b`
- `USER32!SetWindowLongPtrW` at `0x180057778`
- `USER32!SetWindowLongPtrW` at `0x180057778`

## pseudocode

```c
HLOCAL __fastcall ListView_OnNCDestroy(__int64 a1)
{
  struct _IMAGELIST *v2; // rcx
  struct _IMAGELIST *v3; // rcx
  struct _IMAGELIST *v4; // rcx
  void *v5; // rcx
  struct _DPA *v6; // rcx
  struct _DPA *v7; // rcx
  struct _DPA *v8; // rbx
  void *v9; // rcx

  _InterlockedDecrement(&g_dwWindowCount);
  if ( (*(_BYTE *)(a1 + 16) & 0x40) == 0 || (*(_BYTE *)(a1 + 76) & 4) != 0 )
  {
    v2 = *(struct _IMAGELIST **)(a1 + 480);
    if ( v2 )
    {
      if ( v2 != *(struct _IMAGELIST **)(a1 + 272) && v2 != *(struct _IMAGELIST **)(a1 + 232) )
        ImageList_Destroy(v2);
    }
  }
  if ( (*(_BYTE *)(a1 + 16) & 0x40) == 0 )
  {
    v3 = *(struct _IMAGELIST **)(a1 + 272);
    if ( v3 )
      ImageList_Destroy(v3);
    v4 = *(struct _IMAGELIST **)(a1 + 232);
    if ( v4 )
      ImageList_Destroy(v4);
  }
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 496) + 16LL))(*(_QWORD *)(a1 + 496));
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 504) + 16LL))(*(_QWORD *)(a1 + 504));
    *(_DWORD *)(a1 + 512) = 0;
  }
  ListView_ReleaseBkImage(a1);
  v5 = *(void **)(a1 + 112);
  if ( v5 )
    DeleteObject(v5);
  v6 = *(struct _DPA **)(a1 + 64);
  if ( v6 )
    DPA_Destroy(v6);
  v7 = *(struct _DPA **)(a1 + 288);
  if ( v7 )
    DPA_Destroy(v7);
  v8 = *(struct _DPA **)(a1 + 432);
  DPA_EnumCallback(v8, ListView_RDestroyColumn, 0);
  DPA_Destroy(v8);
  v9 = *(void **)(a1 + 640);
  *(_QWORD *)(a1 + 432) = 0;
  if ( v9 )
    LocalFree(v9);
  SetWindowLongPtrW(*(HWND *)a1, 0, 0);
  return LocalFree((HLOCAL)a1);
}

```

## disassembly

```asm
0x180057658  mov     [rsp+arg_0], rbx
0x18005765d  push    rdi
0x18005765e  sub     rsp, 20h
0x180057662  lock dec cs:g_dwWindowCount
0x180057669  mov     rdi, rcx
0x18005766c  test    byte ptr [rcx+10h], 40h
0x180057670  jz      short loc_180057678
0x180057672  test    byte ptr [rcx+4Ch], 4
0x180057676  jz      short loc_18005769B
0x180057678  mov     rcx, [rcx+1E0h]; himl
0x18005767f  test    rcx, rcx
0x180057682  jz      short loc_18005769B
0x180057684  cmp     rcx, [rdi+110h]
0x18005768b  jz      short loc_18005769B
0x18005768d  cmp     rcx, [rdi+0E8h]
0x180057694  jz      short loc_18005769B
0x180057696  call    ImageList_Destroy
0x18005769b  test    byte ptr [rdi+10h], 40h
0x18005769f  jnz     short loc_1800576C3
0x1800576a1  mov     rcx, [rdi+110h]; himl
0x1800576a8  test    rcx, rcx
0x1800576ab  jz      short loc_1800576B2
0x1800576ad  call    ImageList_Destroy
0x1800576b2  mov     rcx, [rdi+0E8h]; himl
0x1800576b9  test    rcx, rcx
0x1800576bc  jz      short loc_1800576C3
0x1800576be  call    ImageList_Destroy
0x1800576c3  test    dword ptr [rdi+10h], 1000h
0x1800576ca  jz      short loc_1800576FC
0x1800576cc  mov     rcx, [rdi+1F0h]
0x1800576d3  mov     rax, [rcx]
0x1800576d6  mov     rax, [rax+10h]
0x1800576da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576df  mov     rcx, [rdi+1F8h]
0x1800576e6  mov     rax, [rcx]
0x1800576e9  mov     rax, [rax+10h]
0x1800576ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800576f2  mov     dword ptr [rdi+200h], 0
0x1800576fc  mov     rcx, rdi
0x1800576ff  call    ListView_ReleaseBkImage
0x180057704  mov     rcx, [rdi+70h]; ho
0x180057708  test    rcx, rcx
0x18005770b  jz      short loc_180057713
0x18005770d  call    cs:__imp_DeleteObject
0x180057713  mov     rcx, [rdi+40h]; hdpa
0x180057717  test    rcx, rcx
0x18005771a  jz      short loc_180057721
0x18005771c  call    DPA_Destroy
0x180057721  mov     rcx, [rdi+120h]; hdpa
0x180057728  test    rcx, rcx
0x18005772b  jz      short loc_180057732
0x18005772d  call    DPA_Destroy
0x180057732  mov     rbx, [rdi+1B0h]
0x180057739  lea     rdx, ListView_RDestroyColumn; pfnCB
0x180057740  mov     rcx, rbx; hdpa
0x180057743  xor     r8d, r8d; pData
0x180057746  call    DPA_EnumCallback
0x18005774b  mov     rcx, rbx; hdpa
0x18005774e  call    DPA_Destroy
0x180057753  mov     rcx, [rdi+280h]; hMem
0x18005775a  mov     qword ptr [rdi+1B0h], 0
0x180057765  test    rcx, rcx
0x180057768  jz      short loc_180057770
0x18005776a  call    cs:__imp_LocalFree
0x180057770  mov     rcx, [rdi]; hWnd
0x180057773  xor     r8d, r8d; dwNewLong
0x180057776  xor     edx, edx; nIndex
0x180057778  call    cs:__imp_SetWindowLongPtrW
0x18005777e  mov     rcx, rdi
0x180057781  mov     rbx, [rsp+28h+arg_0]
0x180057786  add     rsp, 20h
0x18005778a  pop     rdi
0x18005778b  jmp     cs:__imp_LocalFree
```
