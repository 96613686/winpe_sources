# VerifyFileIsTrustedAndInPackage

- ea: `0x180023350`
- end: `0x18002358f`
- name: `VerifyFileIsTrustedAndInPackage`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000e214`
- `0x18000e234`
- `0x180011300`
- `0x180023350`
- `0x180097688`
- `0x1800afa28`
- `0x1800afe14`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002343a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023559`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800233db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002343a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023559`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023394`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023394`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002342a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023497`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023549`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002342a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023497`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180023549`

## string_xrefs

- `0x1800233bb`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18002340e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18002347b`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall VerifyFileIsTrustedAndInPackage(unsigned __int16 *a1, __int64 a2, int *a3)
{
  char *FileW; // rbx
  const char *v7; // r9
  unsigned int LastError; // edi
  __int64 result; // rax
  int WindowsPplTrustLabelSid; // eax
  bool v11; // r8
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  const char *v15; // r9
  __int64 v16; // r8
  char v17; // al
  bool v18; // zf
  int v19; // eax
  int v20; // [rsp+20h] [rbp-78h]
  PSID pSid; // [rsp+40h] [rbp-58h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-50h] BYREF
  __int128 v23; // [rsp+60h] [rbp-38h] BYREF
  __int64 v24; // [rsp+70h] [rbp-28h]
  __int64 v25; // [rsp+78h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v27; // [rsp+B8h] [rbp+20h] BYREF

  FileW = (char *)CreateFileW(a1, 0x20000u, 1u, 0, 3u, 0, 0);
  v22[1] = FileW;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    pSid = 0;
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&pSid);
    v12 = WindowsPplTrustLabelSid;
    if ( WindowsPplTrustLabelSid >= 0 )
    {
      LOBYTE(v27) = 0;
      try
      {
        v13 = TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(a1, pSid, v11, (bool *)&v27);
        v14 = v13;
        if ( v13 >= 0 )
        {
          v23 = 0;
          v24 = 0;
          v25 = 0;
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)(a2 + 2 * v16) );
          std::wstring::_Construct<1,unsigned short const *>(&v23, a2, v16);
          CreatePackageInformation(v22, &v23);
          v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 *))(*(_QWORD *)v22[0] + 8LL))(v22[0], a1);
          if ( !(_BYTE)v27 || (v18 = v17 == 0, v19 = 1, v18) )
            v19 = 0;
          *a3 = v19;
          if ( v22[0] )
            (**(void (__fastcall ***)(_QWORD, __int64))v22[0])(v22[0], 1);
          if ( pSid )
            FreeSid(pSid);
          CloseHandle(FileW);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x397,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v13,
            v20);
          if ( pSid )
            FreeSid(pSid);
          CloseHandle(FileW);
          result = v14;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x3A0,
                               (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                               v15);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)WindowsPplTrustLabelSid,
        v20);
      if ( pSid )
        FreeSid(pSid);
      CloseHandle(FileW);
      return v12;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x38D,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                  v7);
    if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(FileW);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180023350  mov     rax, rsp
0x180023353  mov     [rax+8], rbx
0x180023357  mov     [rax+10h], rsi
0x18002335b  mov     [rax+18h], rdi
0x18002335f  push    r12
0x180023361  push    r14
0x180023363  push    r15
0x180023365  sub     rsp, 80h
0x18002336c  mov     r15, r8
0x18002336f  mov     r14, rdx
0x180023372  mov     rsi, rcx
0x180023375  xor     r12d, r12d
0x180023378  mov     [rax-68h], r12
0x18002337c  mov     [rax-70h], r12d
0x180023380  mov     dword ptr [rax-78h], 3
0x180023387  xor     r9d, r9d; lpSecurityAttributes
0x18002338a  mov     edx, 20000h; dwDesiredAccess
0x18002338f  lea     r8d, [r12+1]; dwShareMode
0x180023394  call    cs:__imp_CreateFileW
0x18002339b  nop     dword ptr [rax+rax+00h]
0x1800233a0  mov     rbx, rax
0x1800233a3  mov     [rsp+98h+var_48], rax
0x1800233a8  inc     rax
0x1800233ab  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800233b1  jnz     short loc_1800233EE
0x1800233b3  mov     rcx, [rsp+98h]; this
0x1800233bb  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800233c2  mov     edx, 38Dh; void *
0x1800233c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800233cc  mov     edi, eax
0x1800233ce  lea     rcx, [rbx-1]
0x1800233d2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800233d6  ja      short loc_1800233E7
0x1800233d8  mov     rcx, rbx; hObject
0x1800233db  call    cs:__imp_CloseHandle
0x1800233e2  nop     dword ptr [rax+rax+00h]
0x1800233e7  mov     eax, edi
0x1800233e9  jmp     loc_180023570
0x1800233ee  mov     [rsp+98h+pSid], r12
0x1800233f3  lea     rcx, [rsp+98h+pSid]; Sid
0x1800233f8  call    ?GetWindowsPplTrustLabelSid@TrustLabelAceHelpers@@SAJPEAPEAX@Z; TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(void * *)
0x1800233fd  mov     edi, eax
0x1800233ff  test    eax, eax
0x180023401  jns     short loc_18002344D
0x180023403  mov     rcx, [rsp+98h]; this
0x18002340b  mov     r9d, eax; char *
0x18002340e  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180023415  mov     edx, 390h; void *
0x18002341a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002341f  nop
0x180023420  mov     rcx, [rsp+98h+pSid]; pSid
0x180023425  test    rcx, rcx
0x180023428  jz      short loc_180023437
0x18002342a  call    cs:__imp_FreeSid
0x180023431  nop     dword ptr [rax+rax+00h]
0x180023436  nop
0x180023437  mov     rcx, rbx; hObject
0x18002343a  call    cs:__imp_CloseHandle
0x180023441  nop     dword ptr [rax+rax+00h]
0x180023446  mov     eax, edi
0x180023448  jmp     loc_180023570
0x18002344d  mov     byte ptr [rsp+98h+arg_18], r12b
0x180023455  lea     r9, [rsp+98h+arg_18]; bool *
0x18002345d  mov     rdx, [rsp+98h+pSid]; void *
0x180023462  mov     rcx, rsi; unsigned __int16 *
0x180023465  call    ?VerifyTrustSidPresentOnFilesystemObject@TrustLabelAceHelpers@@SAJPEBGPEAX_NPEA_N@Z; TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(ushort const *,void *,bool,bool *)
0x18002346a  mov     edi, eax
0x18002346c  test    eax, eax
0x18002346e  jns     short loc_1800234BA
0x180023470  mov     rcx, [rsp+98h]; this
0x180023478  mov     r9d, eax; char *
0x18002347b  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180023482  mov     edx, 397h; void *
0x180023487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002348c  nop
0x18002348d  mov     rcx, [rsp+98h+pSid]; pSid
0x180023492  test    rcx, rcx
0x180023495  jz      short loc_1800234A4
0x180023497  call    cs:__imp_FreeSid
0x18002349e  nop     dword ptr [rax+rax+00h]
0x1800234a3  nop
0x1800234a4  mov     rcx, rbx; hObject
0x1800234a7  call    cs:__imp_CloseHandle
0x1800234ae  nop     dword ptr [rax+rax+00h]
0x1800234b3  mov     eax, edi
0x1800234b5  jmp     loc_180023570
0x1800234ba  xorps   xmm0, xmm0
0x1800234bd  movups  [rsp+98h+var_38], xmm0
0x1800234c2  mov     [rsp+98h+var_28], r12
0x1800234c7  mov     [rsp+98h+var_20], r12
0x1800234cc  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800234d0  inc     r8
0x1800234d3  cmp     [r14+r8*2], r12w
0x1800234d8  jnz     short loc_1800234D0
0x1800234da  mov     rdx, r14
0x1800234dd  lea     rcx, [rsp+98h+var_38]
0x1800234e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800234e7  lea     rdx, [rsp+98h+var_38]
0x1800234ec  lea     rcx, [rsp+98h+var_50]
0x1800234f1  call    ?CreatePackageInformation@@YA?AV?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; CreatePackageInformation(std::wstring)
0x1800234f6  nop
0x1800234f7  mov     rcx, [rsp+98h+var_50]
0x1800234fc  mov     rax, [rcx]
0x1800234ff  mov     rdx, rsi
0x180023502  mov     rax, [rax+8]
0x180023506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002350b  cmp     byte ptr [rsp+98h+arg_18], r12b
0x180023513  jz      short loc_18002351E
0x180023515  test    al, al
0x180023517  mov     eax, 1
0x18002351c  jnz     short loc_180023521
0x18002351e  mov     eax, r12d
0x180023521  mov     [r15], eax
0x180023524  mov     rcx, [rsp+98h+var_50]
0x180023529  test    rcx, rcx
0x18002352c  jz      short loc_18002353F
0x18002352e  mov     rax, [rcx]
0x180023531  mov     edx, 1
0x180023536  mov     rax, [rax]
0x180023539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002353e  nop
0x18002353f  mov     rcx, [rsp+98h+pSid]; pSid
0x180023544  test    rcx, rcx
0x180023547  jz      short loc_180023556
0x180023549  call    cs:__imp_FreeSid
0x180023550  nop     dword ptr [rax+rax+00h]
0x180023555  nop
0x180023556  mov     rcx, rbx; hObject
0x180023559  call    cs:__imp_CloseHandle
0x180023560  nop     dword ptr [rax+rax+00h]
0x180023565  xor     eax, eax
0x180023567  jmp     short loc_180023570
0x180023569  mov     eax, [rsp+98h+arg_18]
0x180023570  lea     r11, [rsp+98h+var_18]
0x180023578  mov     rbx, [r11+20h]
0x18002357c  mov     rsi, [r11+28h]
0x180023580  mov     rdi, [r11+30h]
0x180023584  mov     rsp, r11
0x180023587  pop     r15
0x180023589  pop     r14
0x18002358b  pop     r12
0x18002358d  retn
```
