# CAdvanced::UpdateParamDisplay(void)

- ea: `0x180009fd0`
- end: `0x18000a1ad`
- name: `?UpdateParamDisplay@CAdvanced@@AEAAXXZ`
- size: `477`
- prototype: `void __fastcall(CAdvanced *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000967c`
- `0x180009730`
- `0x180009de8`

## callees

- `0x180001f90`
- `0x180009fd0`
- `0x18000ae10`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a122`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000a122`
- `USER32!SendMessageW` at `0x18000a026`
- `USER32!SendMessageW` at `0x18000a045`
- `USER32!SendMessageW` at `0x18000a0f2`
- `USER32!SendMessageW` at `0x18000a116`
- `USER32!SendMessageW` at `0x18000a149`
- `USER32!SendMessageW` at `0x18000a173`
- `USER32!SendMessageW` at `0x18000a026`
- `USER32!SendMessageW` at `0x18000a045`
- `USER32!SendMessageW` at `0x18000a0f2`
- `USER32!SendMessageW` at `0x18000a116`
- `USER32!SendMessageW` at `0x18000a149`
- `USER32!SendMessageW` at `0x18000a173`
- `USER32!SetWindowTextW` at `0x18000a181`
- `USER32!SetWindowTextW` at `0x18000a181`

## pseudocode

```c
void __fastcall CAdvanced::UpdateParamDisplay(CAdvanced *this)
{
  __int64 v1; // rax
  int *v2; // rdi
  CAdvanced *v3; // rbx
  WCHAR *v4; // rdx
  HWND v5; // rcx
  WPARAM v6; // r8
  CValue *v7; // rcx
  const WCHAR *v8; // rbp
  unsigned int v9; // edi
  int v10; // esi
  const WCHAR *v11; // rax
  WCHAR String[16]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v13[256]; // [rsp+40h] [rbp-238h] BYREF

  v1 = *((_QWORD *)this + 3);
  v2 = (int *)((char *)this + 216);
  *((_DWORD *)this + 60) = 1;
  v3 = this;
  if ( *(_DWORD *)(v1 + 256) )
  {
    SendMessageW(**((HWND **)this + 19), 0xF1u, *v2, 0);
    SendMessageW(**((HWND **)v3 + 20), 0xF1u, *v2 == 0, 0);
    this = v3;
  }
  if ( !*(_DWORD *)(*((_QWORD *)v3 + 3) + 256LL) || *v2 )
  {
    v7 = (CAdvanced *)((char *)this + 200);
    if ( *((_DWORD *)v3 + 49) == 1 )
    {
      CValue::ToString(v7, String, 0x10u);
      v5 = (HWND)SendMessageW(*((HWND *)v3 + 21), 0x46Au, 0, 0);
      v4 = String;
      goto LABEL_22;
    }
    if ( *((_DWORD *)v3 + 49) != 2 )
    {
      if ( *((_DWORD *)v3 + 49) == 3 )
      {
        CValue::ToString(v7, v13, 0x100u);
        v4 = v13;
        goto LABEL_9;
      }
      goto LABEL_23;
    }
    v8 = (const WCHAR *)*((_QWORD *)v3 + 29);
    v9 = 0;
    v10 = SendMessageW(**((HWND **)v3 + 18), 0x146u, 0, 0);
    if ( v10 <= 0 )
    {
LABEL_18:
      v9 = 0;
    }
    else
    {
      while ( 1 )
      {
        v11 = (const WCHAR *)SendMessageW(**((HWND **)v3 + 18), 0x150u, v9, 0);
        if ( !lstrcmpiW(v11, v8) )
          break;
        if ( (int)++v9 >= v10 )
          goto LABEL_18;
      }
    }
    v6 = v9;
LABEL_20:
    SendMessageW(**((HWND **)v3 + 18), 0x14Eu, v6, 0);
    goto LABEL_23;
  }
  switch ( *((_DWORD *)v3 + 49) )
  {
    case 1:
LABEL_8:
      v4 = (WCHAR *)&dword_18001520C;
LABEL_9:
      v5 = (HWND)**((_QWORD **)v3 + 17);
LABEL_22:
      SetWindowTextW(v5, v4);
      break;
    case 2:
      v6 = -1;
      goto LABEL_20;
    case 3:
      goto LABEL_8;
  }
LABEL_23:
  *((_DWORD *)v3 + 60) = 0;
}

```

## disassembly

```asm
0x180009fd0  push    rbx
0x180009fd2  push    rbp
0x180009fd3  push    rsi
0x180009fd4  push    rdi
0x180009fd5  sub     rsp, 258h
0x180009fdc  mov     rax, cs:__security_cookie
0x180009fe3  xor     rax, rsp
0x180009fe6  mov     [rsp+278h+var_38], rax
0x180009fee  mov     rax, [rcx+18h]
0x180009ff2  lea     rdi, [rcx+0D8h]
0x180009ff9  mov     dword ptr [rcx+0F0h], 1
0x18000a003  mov     rbx, rcx
0x18000a006  cmp     dword ptr [rax+100h], 0
0x18000a00d  jz      short loc_18000A04E
0x18000a00f  mov     rcx, [rcx+98h]
0x18000a016  mov     esi, 0F1h
0x18000a01b  movsxd  r8, dword ptr [rdi]; wParam
0x18000a01e  xor     r9d, r9d; lParam
0x18000a021  mov     edx, esi; Msg
0x18000a023  mov     rcx, [rcx]; hWnd
0x18000a026  call    cs:__imp_SendMessageW
0x18000a02c  mov     rcx, [rbx+0A0h]
0x18000a033  xor     r8d, r8d
0x18000a036  cmp     [rdi], r8d
0x18000a039  mov     edx, esi; Msg
0x18000a03b  setz    r8b; wParam
0x18000a03f  xor     r9d, r9d; lParam
0x18000a042  mov     rcx, [rcx]; hWnd
0x18000a045  call    cs:__imp_SendMessageW
0x18000a04b  mov     rcx, rbx
0x18000a04e  mov     rax, [rbx+18h]
0x18000a052  cmp     dword ptr [rax+100h], 0
0x18000a059  jz      short loc_18000A09B
0x18000a05b  cmp     dword ptr [rdi], 0
0x18000a05e  jnz     short loc_18000A09B
0x18000a060  mov     ecx, [rbx+0C4h]
0x18000a066  sub     ecx, 1
0x18000a069  jz      short loc_18000A079
0x18000a06b  sub     ecx, 1
0x18000a06e  jz      short loc_18000A08F
0x18000a070  cmp     ecx, 1
0x18000a073  jnz     loc_18000A187
0x18000a079  lea     rdx, dword_18001520C
0x18000a080  mov     rcx, [rbx+88h]
0x18000a087  mov     rcx, [rcx]
0x18000a08a  jmp     loc_18000A181
0x18000a08f  xor     r9d, r9d
0x18000a092  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a096  jmp     loc_18000A13A
0x18000a09b  mov     edx, [rbx+0C4h]
0x18000a0a1  add     rcx, 0C8h; this
0x18000a0a8  sub     edx, 1
0x18000a0ab  jz      loc_18000A151
0x18000a0b1  sub     edx, 1
0x18000a0b4  jz      short loc_18000A0D6
0x18000a0b6  cmp     edx, 1
0x18000a0b9  jnz     loc_18000A187
0x18000a0bf  mov     r8d, 100h; unsigned int
0x18000a0c5  lea     rdx, [rsp+278h+var_238]; unsigned __int16 *
0x18000a0ca  call    ?ToString@CValue@@QEAAHPEAGI@Z; CValue::ToString(ushort *,uint)
0x18000a0cf  lea     rdx, [rsp+278h+var_238]
0x18000a0d4  jmp     short loc_18000A080
0x18000a0d6  mov     rcx, [rbx+90h]
0x18000a0dd  xor     r9d, r9d; lParam
0x18000a0e0  mov     rbp, [rbx+0E8h]
0x18000a0e7  xor     r8d, r8d; wParam
0x18000a0ea  mov     edx, 146h; Msg
0x18000a0ef  mov     rcx, [rcx]; hWnd
0x18000a0f2  call    cs:__imp_SendMessageW
0x18000a0f8  xor     edi, edi
0x18000a0fa  mov     rsi, rax
0x18000a0fd  test    eax, eax
0x18000a0ff  jle     short loc_18000A132
0x18000a101  mov     rcx, [rbx+90h]
0x18000a108  xor     r9d, r9d; lParam
0x18000a10b  mov     r8d, edi; wParam
0x18000a10e  mov     edx, 150h; Msg
0x18000a113  mov     rcx, [rcx]; hWnd
0x18000a116  call    cs:__imp_SendMessageW
0x18000a11c  mov     rcx, rax; lpString1
0x18000a11f  mov     rdx, rbp; lpString2
0x18000a122  call    cs:__imp_lstrcmpiW
0x18000a128  test    eax, eax
0x18000a12a  jz      short loc_18000A134
0x18000a12c  inc     edi
0x18000a12e  cmp     edi, esi
0x18000a130  jl      short loc_18000A101
0x18000a132  xor     edi, edi
0x18000a134  mov     r8d, edi; wParam
0x18000a137  xor     r9d, r9d; lParam
0x18000a13a  mov     rcx, [rbx+90h]
0x18000a141  mov     edx, 14Eh; Msg
0x18000a146  mov     rcx, [rcx]; hWnd
0x18000a149  call    cs:__imp_SendMessageW
0x18000a14f  jmp     short loc_18000A187
0x18000a151  mov     r8d, 10h; unsigned int
0x18000a157  lea     rdx, [rsp+278h+String]; unsigned __int16 *
0x18000a15c  call    ?ToString@CValue@@QEAAHPEAGI@Z; CValue::ToString(ushort *,uint)
0x18000a161  mov     rcx, [rbx+0A8h]; hWnd
0x18000a168  xor     r9d, r9d; lParam
0x18000a16b  xor     r8d, r8d; wParam
0x18000a16e  mov     edx, 46Ah; Msg
0x18000a173  call    cs:__imp_SendMessageW
0x18000a179  mov     rcx, rax; hWnd
0x18000a17c  lea     rdx, [rsp+278h+String]; lpString
0x18000a181  call    cs:__imp_SetWindowTextW
0x18000a187  mov     dword ptr [rbx+0F0h], 0
0x18000a191  mov     rcx, [rsp+278h+var_38]
0x18000a199  xor     rcx, rsp; StackCookie
0x18000a19c  call    __security_check_cookie
0x18000a1a1  add     rsp, 258h
0x18000a1a8  pop     rdi
0x18000a1a9  pop     rsi
0x18000a1aa  pop     rbp
0x18000a1ab  pop     rbx
0x18000a1ac  retn
```
