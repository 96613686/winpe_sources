# CMessageContextMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x18001be60`
- end: `0x18001c017`
- name: `?InvokeCommand@CMessageContextMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(CMessageContextMenu *__hidden this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001be60`
- `0x18001c020`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001be99`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001beb6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bef2`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf16`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf33`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf4d`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf67`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf81`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf9e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001be99`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001beb6`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bef2`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf16`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf33`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf4d`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf67`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf81`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18001bf9e`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001bff1`
- `api-ms-win-shcore-thread-l1-1-0!SHCreateThread` at `0x18001bff1`

## string_xrefs

- `0x18001beaf`: `delete`
- `0x18001bf7a`: `movetofolder`
- `0x18001bf94`: `copytofolder`

## pseudocode

```c
__int64 __fastcall CMessageContextMenu::InvokeCommand(CMessageContextMenu *this, struct _CMINVOKECOMMANDINFO *a2)
{
  int lpVerb_low; // ebx
  __int64 v6; // rcx
  char *v7; // rsi
  CMessageContextMenu *v8; // rcx

  if ( !a2 )
    return 2147500035LL;
  if ( !WORD1(a2->lpVerb) )
  {
    lpVerb_low = LOWORD(a2->lpVerb);
    goto LABEL_26;
  }
  if ( (unsigned int)_o__stricmp(a2->lpVerb, "open") )
  {
    if ( !(unsigned int)_o__stricmp(a2->lpVerb, "delete") )
    {
      v6 = *((_QWORD *)this + 9);
      if ( !v6 )
      {
        lpVerb_low = 99;
        goto LABEL_26;
      }
      return (*(__int64 (__fastcall **)(__int64, struct _CMINVOKECOMMANDINFO *))(*(_QWORD *)v6 + 32LL))(v6, a2);
    }
    if ( (unsigned int)_o__stricmp(a2->lpVerb, "copy") )
    {
      if ( !(unsigned int)_o__stricmp(a2->lpVerb, "forward") )
      {
        lpVerb_low = 7;
        goto LABEL_26;
      }
      if ( !(unsigned int)_o__stricmp(a2->lpVerb, "reply") )
      {
        lpVerb_low = 5;
        goto LABEL_26;
      }
      if ( !(unsigned int)_o__stricmp(a2->lpVerb, "replyall") )
      {
        lpVerb_low = 6;
        goto LABEL_26;
      }
      if ( !(unsigned int)_o__stricmp(a2->lpVerb, "print") )
      {
        lpVerb_low = 2;
        goto LABEL_26;
      }
      if ( !(unsigned int)_o__stricmp(a2->lpVerb, "movetofolder") )
      {
        lpVerb_low = 3;
        goto LABEL_26;
      }
      lpVerb_low = -1;
      if ( (unsigned int)_o__stricmp(a2->lpVerb, "copytofolder") )
        goto LABEL_26;
    }
    else
    {
      v6 = *((_QWORD *)this + 9);
      if ( v6 )
        return (*(__int64 (__fastcall **)(__int64, struct _CMINVOKECOMMANDINFO *))(*(_QWORD *)v6 + 32LL))(v6, a2);
    }
    lpVerb_low = 4;
    goto LABEL_26;
  }
  lpVerb_low = 1;
LABEL_26:
  v7 = (char *)this - 16;
  *((_DWORD *)this + 28) = lpVerb_low;
  v8 = (CMessageContextMenu *)((char *)this - 16);
  *((_QWORD *)this + 13) = a2->hwnd;
  if ( lpVerb_low == 99 )
  {
    CMessageContextMenu::InvokeEmailCommand(v8);
  }
  else
  {
    (*(void (__fastcall **)(CMessageContextMenu *))(*(_QWORD *)v7 + 8LL))(v8);
    if ( !SHCreateThread(CMessageContextMenu::InvokeEmailCommandThread, (char *)this - 16, 0x18u, 0) )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 16LL))((char *)this - 16);
  }
  return 0;
}

```

## disassembly

```asm
0x18001be60  push    rbx
0x18001be62  push    rbp
0x18001be63  push    rsi
0x18001be64  push    rdi
0x18001be65  push    r14
0x18001be67  sub     rsp, 20h
0x18001be6b  xor     r14d, r14d
0x18001be6e  mov     rdi, rdx
0x18001be71  mov     rbp, rcx
0x18001be74  test    rdx, rdx
0x18001be77  jnz     short loc_18001BE83
0x18001be79  mov     eax, 80004003h
0x18001be7e  jmp     loc_18001C00C
0x18001be83  cmp     [rdx+12h], r14w
0x18001be88  jz      loc_18001BFAF
0x18001be8e  mov     rcx, [rdi+10h]
0x18001be92  lea     rdx, aOpen_0; "open"
0x18001be99  call    cs:__imp__o__stricmp
0x18001be9f  test    eax, eax
0x18001bea1  jnz     short loc_18001BEAB
0x18001bea3  lea     ebx, [rax+1]
0x18001bea6  jmp     loc_18001BFB3
0x18001beab  mov     rcx, [rdi+10h]
0x18001beaf  lea     rdx, aDelete_1; "delete"
0x18001beb6  call    cs:__imp__o__stricmp
0x18001bebc  test    eax, eax
0x18001bebe  jnz     short loc_18001BEE7
0x18001bec0  mov     rcx, [rbp+48h]
0x18001bec4  test    rcx, rcx
0x18001bec7  jz      short loc_18001BEDD
0x18001bec9  mov     rax, [rcx]
0x18001becc  mov     rdx, rdi
0x18001becf  mov     rax, [rax+20h]
0x18001bed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed8  jmp     loc_18001C00C
0x18001bedd  mov     ebx, 63h ; 'c'
0x18001bee2  jmp     loc_18001BFB3
0x18001bee7  mov     rcx, [rdi+10h]
0x18001beeb  lea     rdx, aCopy_0; "copy"
0x18001bef2  call    cs:__imp__o__stricmp
0x18001bef8  test    eax, eax
0x18001befa  jnz     short loc_18001BF0B
0x18001befc  mov     rcx, [rbp+48h]
0x18001bf00  test    rcx, rcx
0x18001bf03  jz      loc_18001BFA8
0x18001bf09  jmp     short loc_18001BEC9
0x18001bf0b  mov     rcx, [rdi+10h]
0x18001bf0f  lea     rdx, aForward_0; "forward"
0x18001bf16  call    cs:__imp__o__stricmp
0x18001bf1c  test    eax, eax
0x18001bf1e  jnz     short loc_18001BF28
0x18001bf20  lea     ebx, [rax+7]
0x18001bf23  jmp     loc_18001BFB3
0x18001bf28  mov     rcx, [rdi+10h]
0x18001bf2c  lea     rdx, aReply_0; "reply"
0x18001bf33  call    cs:__imp__o__stricmp
0x18001bf39  test    eax, eax
0x18001bf3b  jnz     short loc_18001BF42
0x18001bf3d  lea     ebx, [rax+5]
0x18001bf40  jmp     short loc_18001BFB3
0x18001bf42  mov     rcx, [rdi+10h]
0x18001bf46  lea     rdx, aReplyall_1; "replyall"
0x18001bf4d  call    cs:__imp__o__stricmp
0x18001bf53  test    eax, eax
0x18001bf55  jnz     short loc_18001BF5C
0x18001bf57  lea     ebx, [rax+6]
0x18001bf5a  jmp     short loc_18001BFB3
0x18001bf5c  mov     rcx, [rdi+10h]
0x18001bf60  lea     rdx, aPrint; "print"
0x18001bf67  call    cs:__imp__o__stricmp
0x18001bf6d  test    eax, eax
0x18001bf6f  jnz     short loc_18001BF76
0x18001bf71  lea     ebx, [rax+2]
0x18001bf74  jmp     short loc_18001BFB3
0x18001bf76  mov     rcx, [rdi+10h]
0x18001bf7a  lea     rdx, aMovetofolder_0; "movetofolder"
0x18001bf81  call    cs:__imp__o__stricmp
0x18001bf87  test    eax, eax
0x18001bf89  jnz     short loc_18001BF90
0x18001bf8b  lea     ebx, [rax+3]
0x18001bf8e  jmp     short loc_18001BFB3
0x18001bf90  mov     rcx, [rdi+10h]
0x18001bf94  lea     rdx, aCopytofolder; "copytofolder"
0x18001bf9b  or      ebx, 0FFFFFFFFh
0x18001bf9e  call    cs:__imp__o__stricmp
0x18001bfa4  test    eax, eax
0x18001bfa6  jnz     short loc_18001BFB3
0x18001bfa8  mov     ebx, 4
0x18001bfad  jmp     short loc_18001BFB3
0x18001bfaf  movzx   ebx, word ptr [rdx+10h]
0x18001bfb3  lea     rsi, [rbp-10h]
0x18001bfb7  mov     [rsi+80h], ebx
0x18001bfbd  mov     rcx, rsi; this
0x18001bfc0  mov     rax, [rdi+8]
0x18001bfc4  mov     [rbp+68h], rax
0x18001bfc8  cmp     ebx, 63h ; 'c'
0x18001bfcb  jnz     short loc_18001BFD4
0x18001bfcd  call    ?InvokeEmailCommand@CMessageContextMenu@@IEAAXXZ; CMessageContextMenu::InvokeEmailCommand(void)
0x18001bfd2  jmp     short loc_18001C00A
0x18001bfd4  mov     rax, [rsi]
0x18001bfd7  mov     rax, [rax+8]
0x18001bfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfe0  xor     r9d, r9d; pfnCallback
0x18001bfe3  lea     rcx, ?InvokeEmailCommandThread@CMessageContextMenu@@KAKPEAX@Z; pfnThreadProc
0x18001bfea  mov     rdx, rsi; pData
0x18001bfed  lea     r8d, [r9+18h]; flags
0x18001bff1  call    cs:__imp_SHCreateThread
0x18001bff7  test    eax, eax
0x18001bff9  jnz     short loc_18001C00A
0x18001bffb  mov     rax, [rsi]
0x18001bffe  mov     rcx, rsi
0x18001c001  mov     rax, [rax+10h]
0x18001c005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c00a  xor     eax, eax
0x18001c00c  add     rsp, 20h
0x18001c010  pop     r14
0x18001c012  pop     rdi
0x18001c013  pop     rsi
0x18001c014  pop     rbp
0x18001c015  pop     rbx
0x18001c016  retn
```
