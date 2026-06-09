# CContainerWnd::RemoveAdditionalMenuItems(void)

- ea: `0x14001962c`
- end: `0x1400196d4`
- name: `?RemoveAdditionalMenuItems@CContainerWnd@@AEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(CContainerWnd *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001653c`

## callees

- `0x140004703`
- `0x14001962c`

## import_xrefs

- `USER32!GetMenuItemInfoW` at `0x1400196ac`
- `USER32!GetMenuItemInfoW` at `0x1400196ac`
- `USER32!DeleteMenu` at `0x14001964d`
- `USER32!DeleteMenu` at `0x140019676`
- `USER32!DeleteMenu` at `0x1400196be`
- `USER32!DeleteMenu` at `0x14001964d`
- `USER32!DeleteMenu` at `0x140019676`
- `USER32!DeleteMenu` at `0x1400196be`

## pseudocode

```c
__int64 __fastcall CContainerWnd::RemoveAdditionalMenuItems(CContainerWnd *this)
{
  HMENU *v1; // rbx
  HMENU v3; // rcx
  struct tagMENUITEMINFOW mii; // [rsp+20h] [rbp-58h] BYREF

  v1 = (HMENU *)((char *)this + 40);
  if ( *((_QWORD *)this + 9) )
  {
    DeleteMenu(*v1, *((_DWORD *)this + 18), 0);
    *((_QWORD *)this + 9) = 0;
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 95) + 46260LL) )
    DeleteMenu(*v1, 0xABu, 0);
  if ( *v1 )
  {
    memset_0(&mii, 0, sizeof(mii));
    v3 = *v1;
    mii.cbSize = 80;
    if ( GetMenuItemInfoW(v3, 0x9Cu, 0, &mii) )
      DeleteMenu(*v1, 0x9Cu, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001962c  mov     [rsp+arg_0], rbx
0x140019631  push    rdi
0x140019632  sub     rsp, 70h
0x140019636  cmp     qword ptr [rcx+48h], 0
0x14001963b  lea     rbx, [rcx+28h]
0x14001963f  mov     rdi, rcx
0x140019642  jz      short loc_14001965B
0x140019644  mov     edx, [rcx+48h]; uPosition
0x140019647  xor     r8d, r8d; uFlags
0x14001964a  mov     rcx, [rbx]; hMenu
0x14001964d  call    cs:__imp_DeleteMenu
0x140019653  mov     qword ptr [rdi+48h], 0
0x14001965b  mov     rax, [rdi+2F8h]
0x140019662  cmp     dword ptr [rax+0B4B4h], 0
0x140019669  jz      short loc_14001967C
0x14001966b  mov     rcx, [rbx]; hMenu
0x14001966e  xor     r8d, r8d; uFlags
0x140019671  mov     edx, 0ABh; uPosition
0x140019676  call    cs:__imp_DeleteMenu
0x14001967c  cmp     qword ptr [rbx], 0
0x140019680  jz      short loc_1400196C4
0x140019682  mov     edi, 50h ; 'P'
0x140019687  lea     rcx, [rsp+78h+mii]; void *
0x14001968c  mov     r8d, edi; Size
0x14001968f  xor     edx, edx; Val
0x140019691  call    memset_0
0x140019696  mov     rcx, [rbx]; hmenu
0x140019699  lea     r9, [rsp+78h+mii]; lpmii
0x14001969e  mov     [rsp+78h+mii.cbSize], edi
0x1400196a2  xor     r8d, r8d; fByPosition
0x1400196a5  mov     edi, 9Ch
0x1400196aa  mov     edx, edi; item
0x1400196ac  call    cs:__imp_GetMenuItemInfoW
0x1400196b2  test    eax, eax
0x1400196b4  jz      short loc_1400196C4
0x1400196b6  mov     rcx, [rbx]; hMenu
0x1400196b9  xor     r8d, r8d; uFlags
0x1400196bc  mov     edx, edi; uPosition
0x1400196be  call    cs:__imp_DeleteMenu
0x1400196c4  mov     rbx, [rsp+78h+arg_0]
0x1400196cc  xor     eax, eax
0x1400196ce  add     rsp, 70h
0x1400196d2  pop     rdi
0x1400196d3  retn
```
