# CToolBar32::GetTooltipStringForControl(HWND__ *,uint,ulong,ushort * *)

- ea: `0x180043638`
- end: `0x1800437aa`
- name: `?GetTooltipStringForControl@CToolBar32@@AEAAHPEAUHWND__@@IKPEAPEAG@Z`
- size: `370`
- prototype: `int(CToolBar32 *__hidden this, HWND, unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180005454`

## callees

- `0x1800056a4`
- `0x18001e4c0`
- `0x18001efc4`
- `0x1800266cc`
- `0x180043638`
- `0x180047ff8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004377f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004377f`
- `USER32!EnumThreadWindows` at `0x180043750`
- `USER32!EnumThreadWindows` at `0x180043750`
- `USER32!GetWindowThreadProcessId` at `0x180043720`
- `USER32!GetWindowThreadProcessId` at `0x180043720`

## pseudocode

```c
__int64 __fastcall CToolBar32::GetTooltipStringForControl(
        CToolBar32 *this,
        LPARAM a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 **a5)
{
  UINT_PTR v5; // rsi
  HWND v7; // rbx
  unsigned int v8; // edx
  unsigned __int64 v9; // r8
  DWORD WindowThreadProcessId; // eax
  __int64 v12; // rax
  SIZE_T v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  DWORD dwProcessId[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM lParam; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+50h] [rbp-B0h]
  int v19; // [rsp+54h] [rbp-ACh]
  _WORD *v20; // [rsp+58h] [rbp-A8h]
  struct tagTOOLINFOW v21; // [rsp+60h] [rbp-A0h] BYREF
  _WORD Src[256]; // [rsp+B0h] [rbp-50h] BYREF

  v5 = a4;
  *(_QWORD *)dwProcessId = 0;
  if ( CAccessible::AccSendMessageTimeout(this, 0, (HWND)a2, 0x423u, 0, 0, (__int64 *)dwProcessId) < 0 )
    return 0;
  v7 = *(HWND *)dwProcessId;
  if ( *(_QWORD *)dwProcessId )
  {
    memset_0(&v21, 0, sizeof(v21));
    Src[0] = 0;
    v21.lpszText = Src;
    v21.cbSize = 64;
    v21.hwnd = (HWND)a2;
    v21.uId = v5;
    if ( (unsigned int)XSend_ToolTip_GetItem(v7, v8, v9, &v21, v15) )
      return 0;
  }
  else
  {
    dwProcessId[0] = 0;
    WindowThreadProcessId = GetWindowThreadProcessId((HWND)a2, dwProcessId);
    v19 = 0;
    v20 = Src;
    lParam = a2;
    v18 = v5;
    Src[0] = 0;
    EnumThreadWindows(WindowThreadProcessId, EnumThreadWindowsProc, (LPARAM)&lParam);
  }
  if ( !Src[0] )
    return 0;
  v12 = -1;
  do
    ++v12;
  while ( Src[v12] );
  v13 = 2LL * ((int)v12 + 1);
  v14 = (unsigned __int16 *)LocalAlloc(0x40u, v13);
  *a5 = v14;
  if ( !v14 )
    return 0;
  memcpy_0(v14, Src, v13);
  return 1;
}

```

## disassembly

```asm
0x180043638  mov     [rsp-8+arg_10], rbx
0x18004363d  push    rbp
0x18004363e  push    rsi
0x18004363f  push    rdi
0x180043640  push    r14
0x180043642  push    r15
0x180043644  lea     rbp, [rsp-1C0h]
0x18004364c  sub     rsp, 2C0h
0x180043653  mov     rax, cs:__security_cookie
0x18004365a  xor     rax, rsp
0x18004365d  mov     [rbp+1E0h+var_30], rax
0x180043664  mov     r14, [rbp+1E0h+arg_20]
0x18004366b  lea     rax, [rsp+2E0h+dwProcessId]
0x180043670  xor     r15d, r15d
0x180043673  mov     [rsp+2E0h+var_2B0], rax; __int64 *
0x180043678  mov     esi, r9d
0x18004367b  mov     rdi, rdx
0x18004367e  mov     r8, rdx; HWND
0x180043681  mov     [rsp+2E0h+var_2B8], r15; __int64
0x180043686  mov     r9d, 423h; unsigned int
0x18004368c  mov     qword ptr [rsp+2E0h+var_2C0], r15; unsigned int
0x180043691  xor     edx, edx; bool
0x180043693  mov     qword ptr [rsp+2E0h+dwProcessId], r15
0x180043698  call    ?AccSendMessageTimeout@CAccessible@@IEAAJ_NPEAUHWND__@@I_K_JPEA_J@Z; CAccessible::AccSendMessageTimeout(bool,HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18004369d  test    eax, eax
0x18004369f  js      short loc_1800436EB
0x1800436a1  mov     rbx, qword ptr [rsp+2E0h+dwProcessId]
0x1800436a6  test    rbx, rbx
0x1800436a9  jz      short loc_180043713
0x1800436ab  xor     edx, edx; Val
0x1800436ad  lea     r8d, [r15+48h]; Size
0x1800436b1  lea     rcx, [rsp+2E0h+var_280]; void *
0x1800436b6  call    memset_0
0x1800436bb  lea     rax, [rbp+1E0h+Src]
0x1800436bf  mov     [rbp+1E0h+Src], r15w
0x1800436c4  lea     r9, [rsp+2E0h+var_280]; struct tagTOOLINFOW *
0x1800436c9  mov     [rbp+1E0h+var_280.lpszText], rax
0x1800436cd  mov     rcx, rbx; HWND
0x1800436d0  mov     [rsp+2E0h+var_280.cbSize], 40h ; '@'
0x1800436d8  mov     [rsp+2E0h+var_280.hwnd], rdi
0x1800436dd  mov     [rsp+2E0h+var_280.uId], rsi
0x1800436e2  call    ?XSend_ToolTip_GetItem@@YAJPEAUHWND__@@I_KPEAUtagTOOLINFOW@@I@Z; XSend_ToolTip_GetItem(HWND__ *,uint,unsigned __int64,tagTOOLINFOW *,uint)
0x1800436e7  test    eax, eax
0x1800436e9  jz      short loc_180043756
0x1800436eb  xor     eax, eax
0x1800436ed  mov     rcx, [rbp+1E0h+var_30]
0x1800436f4  xor     rcx, rsp; StackCookie
0x1800436f7  call    __security_check_cookie
0x1800436fc  mov     rbx, [rsp+2E0h+arg_10]
0x180043704  add     rsp, 2C0h
0x18004370b  pop     r15
0x18004370d  pop     r14
0x18004370f  pop     rdi
0x180043710  pop     rsi
0x180043711  pop     rbp
0x180043712  retn
0x180043713  lea     rdx, [rsp+2E0h+dwProcessId]; lpdwProcessId
0x180043718  mov     [rsp+2E0h+dwProcessId], r15d
0x18004371d  mov     rcx, rdi; hWnd
0x180043720  call    cs:__imp_GetWindowThreadProcessId
0x180043726  lea     rcx, [rbp+1E0h+Src]
0x18004372a  mov     [rsp+2E0h+var_28C], r15d
0x18004372f  mov     [rsp+2E0h+var_288], rcx
0x180043734  lea     r8, [rsp+2E0h+lParam]; lParam
0x180043739  mov     ecx, eax; dwThreadId
0x18004373b  mov     [rsp+2E0h+lParam], rdi
0x180043740  lea     rdx, EnumThreadWindowsProc; lpfn
0x180043747  mov     [rsp+2E0h+var_290], esi
0x18004374b  mov     [rbp+1E0h+Src], r15w
0x180043750  call    cs:__imp_EnumThreadWindows
0x180043756  cmp     [rbp+1E0h+Src], r15w
0x18004375b  jz      short loc_1800436EB
0x18004375d  lea     rdx, [rbp+1E0h+Src]
0x180043761  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043765  inc     rax
0x180043768  cmp     [rdx+rax*2], r15w
0x18004376d  jnz     short loc_180043765
0x18004376f  inc     eax
0x180043771  mov     ecx, 40h ; '@'; uFlags
0x180043776  movsxd  rbx, eax
0x180043779  add     rbx, rbx
0x18004377c  mov     rdx, rbx; uBytes
0x18004377f  call    cs:__imp_LocalAlloc
0x180043785  mov     [r14], rax
0x180043788  test    rax, rax
0x18004378b  jz      loc_1800436EB
0x180043791  mov     r8, rbx; Size
0x180043794  lea     rdx, [rbp+1E0h+Src]; Src
0x180043798  mov     rcx, rax; void *
0x18004379b  call    memcpy_0
0x1800437a0  mov     eax, 1
0x1800437a5  jmp     loc_1800436ED
```
