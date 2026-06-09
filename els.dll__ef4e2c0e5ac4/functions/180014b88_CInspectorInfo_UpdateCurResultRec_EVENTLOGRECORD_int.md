# CInspectorInfo::UpdateCurResultRec(_EVENTLOGRECORD *,int)

- ea: `0x180014b88`
- end: `0x180014c09`
- name: `?UpdateCurResultRec@CInspectorInfo@@QEAAXPEAU_EVENTLOGRECORD@@H@Z`
- size: `129`
- prototype: `void __fastcall(CInspectorInfo *this, struct _EVENTLOGRECORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops, installer_update`

## callers

- `0x18001bd90`
- `0x18001be20`
- `0x18001d134`
- `0x18001d948`
- `0x18001daf4`

## callees

- `0x180014b88`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180014bbf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180014bbf`
- `USER32!GetParent` at `0x180014bd6`
- `USER32!GetParent` at `0x180014bd6`
- `USER32!PostMessageW` at `0x180014bea`
- `USER32!PostMessageW` at `0x180014bea`

## pseudocode

```c
void __fastcall CInspectorInfo::UpdateCurResultRec(CInspectorInfo *this, struct _EVENTLOGRECORD *a2)
{
  _DWORD *v4; // rcx
  int v5; // edi
  HWND v6; // rcx
  HWND Parent; // rax

  v4 = (_DWORD *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    if ( a2 )
    {
      v5 = 0;
      if ( v4[2] == a2->RecordNumber )
      {
LABEL_5:
        operator delete[](v4);
        goto LABEL_6;
      }
    }
LABEL_4:
    v5 = 1;
    if ( !v4 )
      goto LABEL_6;
    goto LABEL_5;
  }
  if ( a2 )
    goto LABEL_4;
  v5 = 0;
LABEL_6:
  v6 = (HWND)*((_QWORD *)this + 1);
  *((_QWORD *)this + 2) = a2;
  if ( v6 )
  {
    if ( v5 )
    {
      Parent = GetParent(v6);
      PostMessageW(Parent, 0x46Cu, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x180014b88  mov     [rsp+arg_0], rbx
0x180014b8d  mov     [rsp+arg_8], rsi
0x180014b92  push    rdi
0x180014b93  sub     rsp, 20h
0x180014b97  mov     rsi, rcx
0x180014b9a  mov     rbx, rdx
0x180014b9d  mov     rcx, [rcx+10h]
0x180014ba1  test    rcx, rcx
0x180014ba4  jz      short loc_180014C00
0x180014ba6  test    rdx, rdx
0x180014ba9  jz      short loc_180014BB5
0x180014bab  mov     eax, [rdx+8]
0x180014bae  xor     edi, edi
0x180014bb0  cmp     [rcx+8], eax
0x180014bb3  jz      short loc_180014BBF
0x180014bb5  mov     edi, 1
0x180014bba  test    rcx, rcx
0x180014bbd  jz      short loc_180014BC5
0x180014bbf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014bc5  mov     rcx, [rsi+8]; hWnd
0x180014bc9  mov     [rsi+10h], rbx
0x180014bcd  test    rcx, rcx
0x180014bd0  jz      short loc_180014BF0
0x180014bd2  test    edi, edi
0x180014bd4  jz      short loc_180014BF0
0x180014bd6  call    cs:__imp_GetParent
0x180014bdc  xor     r9d, r9d; lParam
0x180014bdf  xor     r8d, r8d; wParam
0x180014be2  mov     rcx, rax; hWnd
0x180014be5  mov     edx, 46Ch; Msg
0x180014bea  call    cs:__imp_PostMessageW
0x180014bf0  mov     rbx, [rsp+28h+arg_0]
0x180014bf5  mov     rsi, [rsp+28h+arg_8]
0x180014bfa  add     rsp, 20h
0x180014bfe  pop     rdi
0x180014bff  retn
0x180014c00  test    rbx, rbx
0x180014c03  jnz     short loc_180014BB5
0x180014c05  xor     edi, edi
0x180014c07  jmp     short loc_180014BC5
```
