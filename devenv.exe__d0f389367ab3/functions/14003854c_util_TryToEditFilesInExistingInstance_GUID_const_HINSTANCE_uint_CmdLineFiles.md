# util_TryToEditFilesInExistingInstance(_GUID const &,HINSTANCE__ *,uint,CmdLineFiles * *)

- ea: `0x14003854c`
- end: `0x14003889c`
- name: `?util_TryToEditFilesInExistingInstance@@YAJAEBU_GUID@@PEAUHINSTANCE__@@IPEAPEAUCmdLineFiles@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(const struct _GUID *, HINSTANCE, unsigned int, struct CmdLineFiles **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140002196`
- `0x140033ab0`
- `0x14003854c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14003870b`
- `KERNEL32!GetFileAttributesW` at `0x14003870b`
- `KERNEL32!MultiByteToWideChar` at `0x1400386ab`
- `KERNEL32!MultiByteToWideChar` at `0x1400386e1`
- `KERNEL32!MultiByteToWideChar` at `0x1400386ab`
- `KERNEL32!MultiByteToWideChar` at `0x1400386e1`
- `KERNEL32!GetLastError` at `0x14003871a`
- `KERNEL32!GetLastError` at `0x14003871a`
- `USER32!SetForegroundWindow` at `0x14003862a`
- `USER32!SetForegroundWindow` at `0x14003862a`
- `OLEAUT32!__imp_SysAllocString` at `0x14003867a`
- `OLEAUT32!__imp_SysAllocString` at `0x14003867a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400386b9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1400386b9`
- `OLEAUT32!__imp_SysFreeString` at `0x140038765`
- `OLEAUT32!__imp_SysFreeString` at `0x14003876e`
- `OLEAUT32!__imp_SysFreeString` at `0x140038866`
- `OLEAUT32!__imp_SysFreeString` at `0x14003886f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003887d`
- `OLEAUT32!__imp_SysFreeString` at `0x140038765`
- `OLEAUT32!__imp_SysFreeString` at `0x14003876e`
- `OLEAUT32!__imp_SysFreeString` at `0x140038866`
- `OLEAUT32!__imp_SysFreeString` at `0x14003886f`
- `OLEAUT32!__imp_SysFreeString` at `0x14003887d`
- `OLEAUT32!__imp_GetActiveObject` at `0x140038598`
- `OLEAUT32!__imp_GetActiveObject` at `0x140038598`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x140038666`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x140038666`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall util_TryToEditFilesInExistingInstance(
        const struct _GUID *a1,
        HINSTANCE a2,
        __int64 a3,
        struct CmdLineFiles **a4)
{
  int ActiveObject; // edi
  IUnknown *v6; // rcx
  __int64 v7; // rcx
  struct CmdLineFiles *v8; // r15
  struct CmdLineFiles *v9; // rsi
  struct CmdLineFiles *v10; // r12
  OLECHAR *v11; // rbx
  int cchWideChar; // r13d
  WCHAR *lpWideCharStr; // rax
  OLECHAR *v14; // r14
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  __int64 v17; // rcx
  char v19; // [rsp+30h] [rbp-D0h]
  HWND hWnd; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  IUnknown *ppunk; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v24 = 0;
  ppunk = 0;
  ActiveObject = GetActiveObject(a1, 0, &ppunk);
  v6 = ppunk;
  if ( ActiveObject < 0 || !ppunk )
    goto LABEL_35;
  ActiveObject = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))ppunk->lpVtbl->QueryInterface)(
                   ppunk,
                   &GUID_04a72314_32e9_48e2_9b87_a63603454f3e,
                   &v24);
  if ( ActiveObject < 0 || !v24 )
    goto LABEL_34;
  hWnd = 0;
  v22 = 0;
  ActiveObject = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 112LL))(v24, &v22);
  if ( ActiveObject >= 0 )
  {
    v7 = v22;
    if ( !v22 )
      goto LABEL_10;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 312LL))(v22);
    (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v22 + 216LL))(v22, &hWnd);
    if ( hWnd )
      SetForegroundWindow(hWnd);
  }
  v7 = v22;
LABEL_10:
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v19 = 0;
  v8 = 0;
  v9 = *a4;
  if ( !*a4 )
    goto LABEL_34;
  while ( 1 )
  {
    v10 = (struct CmdLineFiles *)*((_QWORD *)v9 + 5);
    if ( _wfullpath(Buffer, *(const wchar_t **)v9, 0x104u) )
      break;
LABEL_30:
    if ( !v9 )
      goto LABEL_31;
  }
  v11 = SysAllocString(Buffer);
  if ( !v11 )
    ATL::AtlThrowImpl(-2147024882);
  cchWideChar = MultiByteToWideChar(3u, 0, "{7651A703-06E5-11D1-8EBD-00A0C90F26EA}", -1, 0, 0);
  lpWideCharStr = SysAllocStringLen(0, cchWideChar - 1);
  v14 = lpWideCharStr;
  if ( lpWideCharStr
    && MultiByteToWideChar(3u, 0, "{7651A703-06E5-11D1-8EBD-00A0C90F26EA}", -1, lpWideCharStr, cchWideChar) != cchWideChar )
  {
    SysFreeString(v14);
LABEL_51:
    ATL::AtlThrowImpl(-2147024882);
  }
  hWnd = (HWND)v14;
  if ( !v14 )
    goto LABEL_51;
  v22 = 0;
  FileAttributesW = GetFileAttributesW(Buffer);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    ActiveObject = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      ActiveObject = LastError;
  }
  else if ( (FileAttributesW & 0x10) == 0 )
  {
    ActiveObject = (*(__int64 (__fastcall **)(__int64, OLECHAR *, OLECHAR *, __int64 *))(*(_QWORD *)v24 + 200LL))(
                     v24,
                     v14,
                     v11,
                     &v22);
    if ( ActiveObject >= 0 )
    {
      if ( v8 )
        *((_QWORD *)v8 + 5) = v10;
      else
        *a4 = v10;
      free_0(v9);
      v9 = 0;
      v17 = v22;
      if ( !v22 )
        goto LABEL_25;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 72LL))(v22, 0xFFFFFFFFLL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 312LL))(v22);
LABEL_24:
      v17 = v22;
LABEL_25:
      if ( ActiveObject >= 0 )
        v9 = v8;
      v8 = v9;
      v9 = v10;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      SysFreeString(v14);
      SysFreeString(v11);
      goto LABEL_30;
    }
  }
  if ( ActiveObject != -2147024894 )
  {
    if ( ActiveObject < 0 )
      v19 = 1;
    goto LABEL_24;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  SysFreeString(v14);
  SysFreeString(v11);
LABEL_31:
  if ( v19 && ActiveObject != -2147024894 )
    ActiveObject = -2147467259;
LABEL_34:
  v6 = ppunk;
LABEL_35:
  if ( v6 )
    ((void (__fastcall *)(IUnknown *))v6->lpVtbl->Release)(v6);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)ActiveObject;
}

```

## disassembly

```asm
0x14003854c  mov     [rsp-8+arg_8], rbx
0x140038551  push    rbp
0x140038552  push    rsi
0x140038553  push    rdi
0x140038554  push    r12
0x140038556  push    r13
0x140038558  push    r14
0x14003855a  push    r15
0x14003855c  lea     rbp, [rsp-190h]
0x140038564  sub     rsp, 290h
0x14003856b  mov     rax, cs:__security_cookie
0x140038572  xor     rax, rsp
0x140038575  mov     [rbp+1C0h+var_40], rax
0x14003857c  mov     rbx, r9
0x14003857f  mov     [rsp+2C0h+var_288], rbx
0x140038584  xor     r13d, r13d
0x140038587  mov     [rsp+2C0h+var_260], r13
0x14003858c  mov     [rsp+2C0h+ppunk], r13
0x140038591  lea     r8, [rsp+2C0h+ppunk]; ppunk
0x140038596  xor     edx, edx; pvReserved
0x140038598  call    cs:__imp_GetActiveObject
0x14003859e  mov     edi, eax
0x1400385a0  mov     rcx, [rsp+2C0h+ppunk]
0x1400385a5  test    eax, eax
0x1400385a7  js      loc_140038797
0x1400385ad  test    rcx, rcx
0x1400385b0  jz      loc_140038797
0x1400385b6  mov     rax, [rcx]
0x1400385b9  lea     r8, [rsp+2C0h+var_260]
0x1400385be  lea     rdx, _GUID_04a72314_32e9_48e2_9b87_a63603454f3e
0x1400385c5  call    qword ptr [rax]
0x1400385c7  mov     edi, eax
0x1400385c9  test    eax, eax
0x1400385cb  js      loc_140038792
0x1400385d1  mov     rcx, [rsp+2C0h+var_260]
0x1400385d6  test    rcx, rcx
0x1400385d9  jz      loc_140038792
0x1400385df  mov     [rsp+2C0h+hWnd], r13
0x1400385e4  mov     [rsp+2C0h+var_270], r13
0x1400385e9  mov     rax, [rcx]
0x1400385ec  lea     rdx, [rsp+2C0h+var_270]
0x1400385f1  call    qword ptr [rax+70h]
0x1400385f4  mov     edi, eax
0x1400385f6  test    eax, eax
0x1400385f8  js      short loc_140038630
0x1400385fa  mov     rcx, [rsp+2C0h+var_270]
0x1400385ff  test    rcx, rcx
0x140038602  jz      short loc_140038635
0x140038604  mov     rax, [rcx]
0x140038607  call    qword ptr [rax+138h]
0x14003860d  mov     rcx, [rsp+2C0h+var_270]
0x140038612  mov     rax, [rcx]
0x140038615  lea     rdx, [rsp+2C0h+hWnd]
0x14003861a  call    qword ptr [rax+0D8h]
0x140038620  mov     rcx, [rsp+2C0h+hWnd]; hWnd
0x140038625  test    rcx, rcx
0x140038628  jz      short loc_140038630
0x14003862a  call    cs:__imp_SetForegroundWindow
0x140038630  mov     rcx, [rsp+2C0h+var_270]
0x140038635  test    rcx, rcx
0x140038638  jz      short loc_140038640
0x14003863a  mov     rax, [rcx]
0x14003863d  call    qword ptr [rax+10h]
0x140038640  mov     [rsp+2C0h+var_290], r13b
0x140038645  mov     r15, r13
0x140038648  mov     rsi, [rbx]
0x14003864b  test    rsi, rsi
0x14003864e  jz      loc_140038792
0x140038654  mov     r12, [rsi+28h]
0x140038658  mov     r8d, 104h; BufferCount
0x14003865e  mov     rdx, [rsi]; Path
0x140038661  lea     rcx, [rsp+2C0h+Buffer]; Buffer
0x140038666  call    cs:__imp__wfullpath
0x14003866c  test    rax, rax
0x14003866f  jz      loc_140038774
0x140038675  lea     rcx, [rsp+2C0h+Buffer]; psz
0x14003867a  call    cs:__imp_SysAllocString
0x140038680  mov     rbx, rax
0x140038683  mov     [rsp+2C0h+var_280], rax
0x140038688  test    rax, rax
0x14003868b  jz      loc_140038891
0x140038691  mov     [rsp+2C0h+cchWideChar], r13d; cchWideChar
0x140038696  mov     [rsp+2C0h+lpWideCharStr], r13; lpWideCharStr
0x14003869b  or      r9d, 0FFFFFFFFh; cbMultiByte
0x14003869f  lea     r8, a7651a70306e511; "{7651A703-06E5-11D1-8EBD-00A0C90F26EA}"
0x1400386a6  xor     edx, edx; dwFlags
0x1400386a8  lea     ecx, [rdx+3]; CodePage
0x1400386ab  call    cs:__imp_MultiByteToWideChar
0x1400386b1  mov     r13d, eax
0x1400386b4  lea     edx, [rax-1]; ui
0x1400386b7  xor     ecx, ecx; strIn
0x1400386b9  call    cs:__imp_SysAllocStringLen
0x1400386bf  mov     r14, rax
0x1400386c2  test    rax, rax
0x1400386c5  jz      short loc_1400386F0
0x1400386c7  mov     [rsp+2C0h+cchWideChar], r13d; cchWideChar
0x1400386cc  mov     [rsp+2C0h+lpWideCharStr], rax; lpWideCharStr
0x1400386d1  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1400386d5  lea     r8, a7651a70306e511; "{7651A703-06E5-11D1-8EBD-00A0C90F26EA}"
0x1400386dc  xor     edx, edx; dwFlags
0x1400386de  lea     ecx, [rdx+3]; CodePage
0x1400386e1  call    cs:__imp_MultiByteToWideChar
0x1400386e7  cmp     eax, r13d
0x1400386ea  jnz     loc_14003887A
0x1400386f0  mov     [rsp+2C0h+hWnd], r14
0x1400386f5  xor     r13d, r13d
0x1400386f8  test    r14, r14
0x1400386fb  jz      loc_140038883
0x140038701  mov     [rsp+2C0h+var_270], r13
0x140038706  lea     rcx, [rsp+2C0h+Buffer]; lpFileName
0x14003870b  call    cs:__imp_GetFileAttributesW
0x140038711  cmp     eax, 0FFFFFFFFh
0x140038714  jnz     loc_1400387DF
0x14003871a  call    cs:__imp_GetLastError
0x140038720  movzx   edi, ax
0x140038723  or      edi, 80070000h
0x140038729  test    eax, eax
0x14003872b  cmovle  edi, eax
0x14003872e  mov     eax, edi
0x140038730  cmp     edi, 80070002h
0x140038736  jz      loc_140038852
0x14003873c  test    eax, eax
0x14003873e  jns     short loc_140038745
0x140038740  mov     [rsp+2C0h+var_290], 1
0x140038745  mov     rcx, [rsp+2C0h+var_270]
0x14003874a  test    edi, edi
0x14003874c  cmovns  rsi, r15
0x140038750  mov     r15, rsi
0x140038753  mov     rsi, r12
0x140038756  test    rcx, rcx
0x140038759  jz      short loc_140038762
0x14003875b  mov     rax, [rcx]
0x14003875e  call    qword ptr [rax+10h]
0x140038761  nop
0x140038762  mov     rcx, r14; bstrString
0x140038765  call    cs:__imp_SysFreeString
0x14003876b  mov     rcx, rbx; bstrString
0x14003876e  call    cs:__imp_SysFreeString
0x140038774  test    rsi, rsi
0x140038777  jnz     loc_140038654
0x14003877d  cmp     [rsp+2C0h+var_290], r13b
0x140038782  jz      short loc_140038792
0x140038784  mov     eax, 80004005h
0x140038789  cmp     edi, 80070002h
0x14003878f  cmovnz  edi, eax
0x140038792  mov     rcx, [rsp+2C0h+ppunk]
0x140038797  test    rcx, rcx
0x14003879a  jz      short loc_1400387A3
0x14003879c  mov     rax, [rcx]
0x14003879f  call    qword ptr [rax+10h]
0x1400387a2  nop
0x1400387a3  mov     rcx, [rsp+2C0h+var_260]
0x1400387a8  test    rcx, rcx
0x1400387ab  jz      short loc_1400387B3
0x1400387ad  mov     rax, [rcx]
0x1400387b0  call    qword ptr [rax+10h]
0x1400387b3  mov     eax, edi
0x1400387b5  mov     rcx, [rbp+1C0h+var_40]
0x1400387bc  xor     rcx, rsp; StackCookie
0x1400387bf  call    __security_check_cookie
0x1400387c4  mov     rbx, [rsp+2C0h+arg_8]
0x1400387cc  add     rsp, 290h
0x1400387d3  pop     r15
0x1400387d5  pop     r14
0x1400387d7  pop     r13
0x1400387d9  pop     r12
0x1400387db  pop     rdi
0x1400387dc  pop     rsi
0x1400387dd  pop     rbp
0x1400387de  retn
0x1400387df  test    al, 10h
0x1400387e1  jnz     loc_14003872E
0x1400387e7  mov     rcx, [rsp+2C0h+var_260]
0x1400387ec  mov     rax, [rcx]
0x1400387ef  lea     r9, [rsp+2C0h+var_270]
0x1400387f4  mov     r8, rbx
0x1400387f7  mov     rdx, r14
0x1400387fa  call    qword ptr [rax+0C8h]
0x140038800  mov     edi, eax
0x140038802  test    eax, eax
0x140038804  js      loc_14003872E
0x14003880a  test    r15, r15
0x14003880d  jnz     short loc_140038819
0x14003880f  mov     rax, [rsp+2C0h+var_288]
0x140038814  mov     [rax], r12
0x140038817  jmp     short loc_14003881D
0x140038819  mov     [r15+28h], r12
0x14003881d  mov     rcx, rsi; Block
0x140038820  call    free_0
0x140038825  mov     rsi, r13
0x140038828  mov     rcx, [rsp+2C0h+var_270]
0x14003882d  test    rcx, rcx
0x140038830  jz      loc_14003874A
0x140038836  mov     rax, [rcx]
0x140038839  or      edx, 0FFFFFFFFh
0x14003883c  call    qword ptr [rax+48h]
0x14003883f  mov     rcx, [rsp+2C0h+var_270]
0x140038844  mov     rax, [rcx]
0x140038847  call    qword ptr [rax+138h]
0x14003884d  jmp     loc_140038745
0x140038852  mov     rcx, [rsp+2C0h+var_270]
0x140038857  test    rcx, rcx
0x14003885a  jz      short loc_140038863
0x14003885c  mov     rax, [rcx]
0x14003885f  call    qword ptr [rax+10h]
0x140038862  nop
0x140038863  mov     rcx, r14; bstrString
0x140038866  call    cs:__imp_SysFreeString
0x14003886c  mov     rcx, rbx; bstrString
0x14003886f  call    cs:__imp_SysFreeString
0x140038875  jmp     loc_14003877D
0x14003887a  mov     rcx, r14; bstrString
0x14003887d  call    cs:__imp_SysFreeString
0x140038883  mov     ecx, 8007000Eh; int
0x140038888  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003888e  jmp     short $+2
0x140038890  nop
0x140038891  mov     ecx, 8007000Eh; int
0x140038896  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
