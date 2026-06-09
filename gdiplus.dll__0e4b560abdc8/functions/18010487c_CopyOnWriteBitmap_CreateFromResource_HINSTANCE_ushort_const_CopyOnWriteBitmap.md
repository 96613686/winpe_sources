# CopyOnWriteBitmap::CreateFromResource(HINSTANCE__ *,ushort const *,CopyOnWriteBitmap * *)

- ea: `0x18010487c`
- end: `0x180104955`
- name: `?CreateFromResource@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHINSTANCE__@@PEBGPEAPEAV1@@Z`
- size: `217`
- prototype: `__int64 __fastcall(HINSTANCE, const WCHAR *, CopyOnWriteBitmap **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18010495c`

## callees

- `0x180004460`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x1801045a4`
- `0x18010487c`

## import_xrefs

- `USER32!LoadImageW` at `0x1801048b1`
- `USER32!LoadImageW` at `0x1801048b1`
- `GDI32!GetObjectW` at `0x1801048e2`
- `GDI32!GetObjectW` at `0x1801048e2`
- `GDI32!DeleteObject` at `0x18010491e`
- `GDI32!DeleteObject` at `0x18010491e`

## pseudocode

```c
__int64 __fastcall CopyOnWriteBitmap::CreateFromResource(HINSTANCE a1, const WCHAR *a2, CopyOnWriteBitmap **a3)
{
  HBITMAP ImageW; // rdi
  int ObjectW; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  _BYTE pv[112]; // [rsp+30h] [rbp-88h] BYREF

  ImageW = (HBITMAP)LoadImageW(a1, a2, 0, 0, 0, 0x2000u);
  if ( !ImageW )
    return 2;
  memset_0(pv, 0, 0x68u);
  ObjectW = GetObjectW(ImageW, 104, pv);
  if ( ObjectW == 104 )
  {
    v6 = CopyOnWriteBitmap::CreateFromDibSection(ImageW, a3);
  }
  else
  {
    if ( ObjectW != 32 )
    {
      v7 = 2;
      goto LABEL_8;
    }
    v6 = CopyOnWriteBitmap::CreateFromHBITMAP(ImageW, 0, a3);
  }
  v7 = v6;
LABEL_8:
  DeleteObject(ImageW);
  return v7;
}

```

## disassembly

```asm
0x18010487c  mov     [rsp+arg_18], rbx
0x180104881  push    rdi
0x180104882  sub     rsp, 0B0h
0x180104889  mov     rax, cs:__security_cookie
0x180104890  xor     rax, rsp
0x180104893  mov     [rsp+0B8h+var_18], rax
0x18010489b  mov     rbx, r8
0x18010489e  mov     [rsp+0B8h+fuLoad], 2000h; fuLoad
0x1801048a6  and     [rsp+0B8h+var_98], 0
0x1801048ab  xor     r8d, r8d; type
0x1801048ae  xor     r9d, r9d; cx
0x1801048b1  call    cs:__imp_LoadImageW
0x1801048b8  nop     dword ptr [rax+rax+00h]
0x1801048bd  mov     rdi, rax
0x1801048c0  test    rax, rax
0x1801048c3  jz      short loc_18010492C
0x1801048c5  xor     edx, edx; Val
0x1801048c7  lea     rcx, [rsp+0B8h+pv]; void *
0x1801048cc  lea     r8d, [rdx+68h]; Size
0x1801048d0  call    memset_0
0x1801048d5  lea     r8, [rsp+0B8h+pv]; pv
0x1801048da  mov     edx, 68h ; 'h'; c
0x1801048df  mov     rcx, rdi; h
0x1801048e2  call    cs:__imp_GetObjectW
0x1801048e9  nop     dword ptr [rax+rax+00h]
0x1801048ee  cmp     eax, 68h ; 'h'
0x1801048f1  jnz     short loc_180104900
0x1801048f3  mov     rdx, rbx
0x1801048f6  mov     rcx, rdi
0x1801048f9  call    ?CreateFromDibSection@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAPEAV1@@Z; CopyOnWriteBitmap::CreateFromDibSection(HBITMAP__ *,CopyOnWriteBitmap * *)
0x1801048fe  jmp     short loc_180104912
0x180104900  cmp     eax, 20h ; ' '
0x180104903  jnz     short loc_180104916
0x180104905  mov     r8, rbx
0x180104908  xor     edx, edx
0x18010490a  mov     rcx, rdi
0x18010490d  call    ?CreateFromHBITMAP@CopyOnWriteBitmap@@CA?AW4Status@@PEAUHBITMAP__@@PEAUHPALETTE__@@PEAPEAV1@@Z; CopyOnWriteBitmap::CreateFromHBITMAP(HBITMAP__ *,HPALETTE__ *,CopyOnWriteBitmap * *)
0x180104912  mov     ebx, eax
0x180104914  jmp     short loc_18010491B
0x180104916  mov     ebx, 2
0x18010491b  mov     rcx, rdi; ho
0x18010491e  call    cs:__imp_DeleteObject
0x180104925  nop     dword ptr [rax+rax+00h]
0x18010492a  jmp     short loc_180104931
0x18010492c  mov     ebx, 2
0x180104931  mov     eax, ebx
0x180104933  mov     rcx, [rsp+0B8h+var_18]
0x18010493b  xor     rcx, rsp; StackCookie
0x18010493e  call    __security_check_cookie
0x180104943  mov     rbx, [rsp+0B8h+arg_18]
0x18010494b  add     rsp, 0B0h
0x180104952  pop     rdi
0x180104953  retn
```
