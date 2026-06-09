# SQLInstallTranslatorCover

- ea: `0x180009464`
- end: `0x180009600`
- name: `SQLInstallTranslatorCover`
- size: `412`
- prototype: `_BOOL8 __fastcall(_WORD *, WCHAR *, wchar_t *, wchar_t *, unsigned __int16, char *, __int16, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180009660`

## callees

- `0x180004bac`
- `0x180006184`
- `0x180009464`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x180009503`
- `USER32!MessageBoxW` at `0x180009503`
- `USER32!LoadStringW` at `0x1800094bd`
- `USER32!LoadStringW` at `0x1800094e2`
- `USER32!LoadStringW` at `0x1800094bd`
- `USER32!LoadStringW` at `0x1800094e2`

## pseudocode

```c
_BOOL8 __fastcall SQLInstallTranslatorCover(
        _WORD *a1,
        WCHAR *a2,
        wchar_t *a3,
        wchar_t *a4,
        unsigned __int16 a5,
        char *a6,
        __int16 a7,
        int *a8)
{
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // ecx
  char *v11; // rax
  char v13; // [rsp+40h] [rbp-398h] BYREF
  WCHAR Caption[128]; // [rsp+50h] [rbp-388h] BYREF
  WCHAR Buffer[304]; // [rsp+150h] [rbp-288h] BYREF

  if ( a1 && *a1 )
  {
    if ( LoadStringW(g_hResDLL, 0x533u, Buffer, 301) )
    {
      if ( LoadStringW(g_hResDLL, 0x522u, Caption, 128) )
        MessageBoxW(0, Buffer, Caption, 0x10u);
    }
    return 0;
  }
  if ( !a2 || !*a2 )
  {
    v10 = 7;
    goto LABEL_26;
  }
  if ( (unsigned __int16)(a7 - 1) > 1u )
  {
    v10 = 5;
    goto LABEL_26;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( !a2[v9 + 1] )
  {
    v10 = 8;
LABEL_26:
    PostInstError(v10);
    return 0;
  }
  if ( a7 == 2 && (!a4 || !a5) )
  {
    v10 = 2;
    goto LABEL_26;
  }
  if ( a3 )
  {
    do
      ++v8;
    while ( a3[v8] );
    if ( v8 >= 0x104 )
    {
      v10 = 12;
      goto LABEL_26;
    }
  }
  v11 = &v13;
  if ( a6 )
    v11 = a6;
  return (unsigned int)AddTranslator(v8, a2, a3, a4, a5, v11, a7, a8) != 0;
}

```

## disassembly

```asm
0x180009464  push    rbx
0x180009466  push    rsi
0x180009467  push    rdi
0x180009468  sub     rsp, 3C0h
0x18000946f  mov     rax, cs:__security_cookie
0x180009476  xor     rax, rsp
0x180009479  mov     [rsp+3D8h+var_28], rax
0x180009481  mov     rbx, [rsp+3D8h+arg_28]
0x180009489  xor     esi, esi
0x18000948b  mov     rdi, [rsp+3D8h+arg_38]
0x180009493  mov     r11, r9
0x180009496  mov     r10, r8
0x180009499  test    rcx, rcx
0x18000949c  jz      short loc_18000950E
0x18000949e  cmp     [rcx], si
0x1800094a1  jz      short loc_18000950E
0x1800094a3  mov     rcx, cs:g_hResDLL; hInstance
0x1800094aa  lea     r8, [rsp+3D8h+Buffer]; lpBuffer
0x1800094b2  mov     r9d, 12Dh; cchBufferMax
0x1800094b8  mov     edx, 533h; uID
0x1800094bd  call    cs:__imp_LoadStringW
0x1800094c3  test    eax, eax
0x1800094c5  jz      loc_1800095E3
0x1800094cb  mov     rcx, cs:g_hResDLL; hInstance
0x1800094d2  lea     r8, [rsp+3D8h+Caption]; lpBuffer
0x1800094d7  mov     r9d, 80h; cchBufferMax
0x1800094dd  mov     edx, 522h; uID
0x1800094e2  call    cs:__imp_LoadStringW
0x1800094e8  test    eax, eax
0x1800094ea  jz      loc_1800095E3
0x1800094f0  lea     r9d, [rsi+10h]; uType
0x1800094f4  xor     ecx, ecx; hWnd
0x1800094f6  lea     r8, [rsp+3D8h+Caption]; lpCaption
0x1800094fb  lea     rdx, [rsp+3D8h+Buffer]; lpText
0x180009503  call    cs:__imp_MessageBoxW
0x180009509  jmp     loc_1800095E3
0x18000950e  test    rdx, rdx
0x180009511  jz      loc_1800095D9
0x180009517  cmp     [rdx], si
0x18000951a  jz      loc_1800095D9
0x180009520  movzx   r8d, [rsp+3D8h+arg_30]
0x180009529  lea     eax, [r8-1]
0x18000952d  cmp     ax, 1
0x180009531  ja      loc_1800095D2
0x180009537  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000953b  mov     rax, rcx
0x18000953e  inc     rax
0x180009541  cmp     [rdx+rax*2], si
0x180009545  jnz     short loc_18000953E
0x180009547  cmp     [rdx+rax*2+2], si
0x18000954c  jnz     short loc_180009558
0x18000954e  mov     ecx, 8
0x180009553  jmp     loc_1800095DE
0x180009558  movzx   r9d, [rsp+3D8h+arg_20]
0x180009561  mov     eax, 2
0x180009566  cmp     r8w, ax
0x18000956a  jnz     short loc_18000957B
0x18000956c  test    r11, r11
0x18000956f  jz      short loc_180009577
0x180009571  test    r9w, r9w
0x180009575  jnz     short loc_18000957B
0x180009577  mov     ecx, eax
0x180009579  jmp     short loc_1800095DE
0x18000957b  test    r10, r10
0x18000957e  jz      short loc_18000959A
0x180009580  inc     rcx
0x180009583  cmp     [r10+rcx*2], si
0x180009588  jnz     short loc_180009580
0x18000958a  cmp     rcx, 104h
0x180009591  jb      short loc_18000959A
0x180009593  mov     ecx, 0Ch
0x180009598  jmp     short loc_1800095DE
0x18000959a  mov     [rsp+3D8h+var_3A0], rdi
0x18000959f  lea     rax, [rsp+3D8h+var_398]
0x1800095a4  mov     [rsp+3D8h+var_3A8], r8w
0x1800095aa  test    rbx, rbx
0x1800095ad  mov     r8, r10
0x1800095b0  cmovnz  rax, rbx
0x1800095b4  mov     [rsp+3D8h+var_3B0], rax
0x1800095b9  mov     [rsp+3D8h+var_3B8], r9w
0x1800095bf  mov     r9, r11
0x1800095c2  call    AddTranslator
0x1800095c7  test    eax, eax
0x1800095c9  mov     ecx, esi
0x1800095cb  setnz   cl
0x1800095ce  mov     eax, ecx
0x1800095d0  jmp     short loc_1800095E5
0x1800095d2  mov     ecx, 5
0x1800095d7  jmp     short loc_1800095DE
0x1800095d9  mov     ecx, 7
0x1800095de  call    PostInstError
0x1800095e3  xor     eax, eax
0x1800095e5  mov     rcx, [rsp+3D8h+var_28]
0x1800095ed  xor     rcx, rsp; StackCookie
0x1800095f0  call    __security_check_cookie
0x1800095f5  add     rsp, 3C0h
0x1800095fc  pop     rdi
0x1800095fd  pop     rsi
0x1800095fe  pop     rbx
0x1800095ff  retn
```
