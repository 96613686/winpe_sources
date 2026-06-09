# CMediaServerFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18001ef30`
- end: `0x18001efd6`
- name: `?CreateViewObject@CMediaServerFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(CMediaServerFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180019b84`
- `0x18001ef30`

## import_xrefs

- `ext-ms-win-casting-shell-l1-1-0!CreateViewObjectForMediaServerFolder` at `0x18001ef75`
- `ext-ms-win-casting-shell-l1-1-0!CreateViewObjectForMediaServerFolder` at `0x18001ef75`

## pseudocode

```c
__int64 __fastcall CMediaServerFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  int v4; // ebx
  __int64 v5; // rax
  int ViewObjectForMediaServerFolder; // eax

  *a4 = 0;
  v4 = -2147467262;
  v5 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_000214e3_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_000214e3_0000_0000_c000_000000000046.Data1 )
    v5 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_000214e3_0000_0000_c000_000000000046.Data4;
  if ( !v5 )
  {
    ViewObjectForMediaServerFolder = CreateViewObjectForMediaServerFolder(
                                       this & -(__int64)(this != 16),
                                       *(_QWORD *)(this + 96),
                                       a4);
    if ( ViewObjectForMediaServerFolder == -2147467263 )
      ViewObjectForMediaServerFolder = -2147467262;
    v4 = ViewObjectForMediaServerFolder;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v4 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids,
      (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ef30  push    rbx
0x18001ef32  sub     rsp, 20h
0x18001ef36  mov     qword ptr [r9], 0
0x18001ef3d  mov     rdx, rcx
0x18001ef40  mov     rax, [r8]
0x18001ef43  mov     ebx, 80004002h
0x18001ef48  sub     rax, qword ptr cs:_GUID_000214e3_0000_0000_c000_000000000046.Data1
0x18001ef4f  jnz     short loc_18001EF5C
0x18001ef51  mov     rax, [r8+8]
0x18001ef55  sub     rax, qword ptr cs:_GUID_000214e3_0000_0000_c000_000000000046.Data4
0x18001ef5c  test    rax, rax
0x18001ef5f  jnz     short loc_18001EF85
0x18001ef61  lea     rax, [rcx-10h]
0x18001ef65  mov     r8, r9
0x18001ef68  neg     rax
0x18001ef6b  sbb     rcx, rcx
0x18001ef6e  and     rcx, rdx
0x18001ef71  mov     rdx, [rdx+60h]
0x18001ef75  call    cs:__imp_CreateViewObjectForMediaServerFolder
0x18001ef7b  cmp     eax, 80004001h
0x18001ef80  cmovz   eax, ebx
0x18001ef83  mov     ebx, eax
0x18001ef85  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef8c  lea     rax, WPP_GLOBAL_Control
0x18001ef93  cmp     rcx, rax
0x18001ef96  jz      short loc_18001EFCE
0x18001ef98  test    byte ptr [rcx+1Ch], 2
0x18001ef9c  jz      short loc_18001EFCE
0x18001ef9e  movzx   edx, byte ptr [rcx+19h]
0x18001efa2  mov     r8d, ebx
0x18001efa5  sar     r8d, 1Fh
0x18001efa9  and     r8d, 0FFFFFFFDh
0x18001efad  add     r8d, 5
0x18001efb1  cmp     edx, r8d
0x18001efb4  jb      short loc_18001EFCE
0x18001efb6  mov     rcx, [rcx+10h]
0x18001efba  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18001efc1  mov     edx, 14h
0x18001efc6  mov     r9d, ebx
0x18001efc9  call    WPP_SF_d
0x18001efce  mov     eax, ebx
0x18001efd0  add     rsp, 20h
0x18001efd4  pop     rbx
0x18001efd5  retn
```
