# CFileAccessor::Reset(void)

- ea: `0x180003110`
- end: `0x1800034d1`
- name: `?Reset@CFileAccessor@@QEAAJXZ`
- size: `961`
- prototype: `__int64 __fastcall(CFileAccessor *__hidden this)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002c40`
- `0x180003970`
- `0x180007ff0`
- `0x180021770`

## callees

- `0x180002d00`
- `0x180003110`
- `0x180004e60`
- `0x180006430`
- `0x18000e4c8`
- `0x18000fcd0`
- `0x18001e194`
- `0x180020bac`
- `0x18002324c`
- `0x180027010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000323e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000346a`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000323e`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x18000346a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003358`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000333b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000336a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000333b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000336a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003405`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000339b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000339b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800033fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003410`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800033f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000330a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000330a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003149`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180003149`

## string_xrefs

- `0x180003431`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileAccessor::Reset(CFileAccessor *this)
{
  void *v2; // rcx
  char *v3; // rbp
  char *v4; // rsi
  __int64 v5; // rcx
  char *v6; // rsi
  char *v7; // rcx
  unsigned int v8; // esi
  int v9; // edi
  char *v10; // rbp
  int v11; // esi
  void *v12; // rcx
  char *v14; // rsi
  char *v15; // rcx
  DWORD LastError; // edi
  DWORD v17; // edi
  DWORD v18; // edi
  DWORD v19; // edi
  int v20; // edx
  int v21; // eax
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // [rsp+30h] [rbp-1F8h] BYREF
  int v25; // [rsp+34h] [rbp-1F4h]
  char *v26; // [rsp+38h] [rbp-1F0h]
  _BYTE v27[8]; // [rsp+40h] [rbp-1E8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-1E0h]

  v2 = (void *)*((_QWORD *)this + 24);
  if ( v2 != (void *)-1LL )
  {
    if ( !UnregisterWaitEx(v2, *((HANDLE *)this + 26)) && GetLastError() == 997 )
    {
      v15 = (char *)*((_QWORD *)this + 25);
      if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        SetEvent(v15);
        WaitForSingleObject(*((HANDLE *)this + 26), 0xFFFFFFFF);
      }
    }
    *((_QWORD *)this + 24) = -1;
  }
  v3 = (char *)*((_QWORD *)this + 26);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 26) = -1;
  v4 = (char *)*((_QWORD *)this + 25);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v17 = GetLastError();
    CloseHandle(v4);
    SetLastError(v17);
  }
  *((_QWORD *)this + 25) = 0;
  v5 = *((_QWORD *)this + 27);
  if ( v5 )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v5 + 24,
      -1);
    TComPointer<CFileStream>::operator=((_QWORD *)this + 27, 0);
  }
  v6 = (char *)*((_QWORD *)this + 13);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v18 = GetLastError();
    CloseHandle(v6);
    SetLastError(v18);
  }
  *((_QWORD *)this + 13) = -1;
  v7 = (char *)*((_QWORD *)this + 12);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *((_DWORD *)this + 36) )
      WaitForSingleObject(v7, 0xFFFFFFFF);
    v14 = (char *)*((_QWORD *)this + 12);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v19 = GetLastError();
      CloseHandle(v14);
      SetLastError(v19);
    }
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 18) = 0;
  *((_OWORD *)this + 7) = 0;
  *((_OWORD *)this + 8) = 0;
  (*(void (__fastcall **)(char *, const wchar_t *, _QWORD, __int64))(*((_QWORD *)this + 31) + 32LL))(
    (char *)this + 248,
    &qword_18002A7A0,
    0,
    0xFFFFFFFFLL);
  v8 = 0;
  v24 = 0;
  v9 = *((_DWORD *)this + 67);
  v10 = (char *)this + 248;
  v26 = (char *)this + 248;
  while ( 1 )
  {
    v25 = v9;
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_18;
    }
    if ( !(unsigned int)_o_iswspace(*(unsigned __int16 *)(*((_QWORD *)this + 32) + 2LL * v8)) )
      break;
    v24 = ++v8;
    --v9;
  }
  v20 = v9;
  v21 = v9;
  v22 = v9;
  while ( 1 )
  {
    if ( v9 )
    {
      v23 = *(unsigned __int16 *)(*((_QWORD *)v10 + 1) + 2LL * (v8 + v22 - 1));
    }
    else
    {
      v23 = 0;
      v20 = v21;
    }
    v11 = v20;
    if ( !(unsigned int)_o_iswspace(v23) )
      break;
    CLMSubStr::Truncate((CLMSubStr *)&v24, v9 - 1);
    v9 = v25;
    v20 = v25;
    v21 = v25;
    v11 = v25;
    v22 = v25;
    if ( !v25 )
      break;
    v10 = v26;
    v8 = v24;
  }
LABEL_18:
  if ( v11 != *((_DWORD *)this + 67) )
  {
    TLMString<192,64,32767>::TLMString<192,64,32767>(v27, &v24);
    CLMString::operator=((__int64)this + 248, v28);
    TLMString<192,64,32767>::~TLMString<192,64,32767>(v27);
  }
  *(_QWORD *)((char *)this + 684) = 6225920;
  *(_QWORD *)((char *)this + 666) = 0;
  *(_QWORD *)((char *)this + 674) = 0;
  *((_WORD *)this + 341) = 0;
  (*(void (__fastcall **)(char *, const wchar_t *, _QWORD, __int64))(*((_QWORD *)this + 87) + 32LL))(
    (char *)this + 696,
    &qword_18002A7A0,
    0,
    0xFFFFFFFFLL);
  *((_QWORD *)this + 117) = 0;
  *((_DWORD *)this + 215) = 0;
  *((_DWORD *)this + 230) = 0;
  v12 = (void *)*((_QWORD *)this + 116);
  *((_QWORD *)this + 116) = 0;
  if ( v12 )
    LocalFree(v12);
  *((_WORD *)this + 44) = 0;
  *((_BYTE *)this + 90) = 0;
  *((_DWORD *)this + 23) = 0;
  return 0;
}

```

## disassembly

```asm
0x180003110  push    rbx
0x180003112  push    rbp
0x180003113  push    rsi
0x180003114  push    rdi
0x180003115  push    r14
0x180003117  push    r15
0x180003119  sub     rsp, 1F8h
0x180003120  mov     rax, cs:__security_cookie
0x180003127  xor     rax, rsp
0x18000312a  mov     [rsp+228h+var_48], rax
0x180003132  mov     rbx, rcx
0x180003135  mov     rcx, [rcx+0C0h]; WaitHandle
0x18000313c  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180003140  jz      short loc_180003162
0x180003142  mov     rdx, [rbx+0D0h]; CompletionEvent
0x180003149  call    cs:__imp_UnregisterWaitEx
0x18000314f  test    eax, eax
0x180003151  jz      loc_180003375
0x180003157  mov     qword ptr [rbx+0C0h], 0FFFFFFFFFFFFFFFFh
0x180003162  mov     rbp, [rbx+0D0h]
0x180003169  lea     rax, [rbp-1]
0x18000316d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003171  jbe     loc_180003388
0x180003177  mov     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x180003182  mov     rsi, [rbx+0C8h]
0x180003189  lea     rax, [rsi-1]
0x18000318d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003191  jbe     loc_1800033A6
0x180003197  xor     r15d, r15d
0x18000319a  mov     [rbx+0C8h], r15
0x1800031a1  mov     rcx, [rbx+0D8h]
0x1800031a8  test    rcx, rcx
0x1800031ab  jnz     loc_1800033C4
0x1800031b1  mov     rsi, [rbx+68h]
0x1800031b5  lea     rax, [rsi-1]
0x1800031b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800031bd  jbe     loc_1800033E7
0x1800031c3  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x1800031cb  mov     rcx, [rbx+60h]; hHandle
0x1800031cf  lea     rax, [rcx-1]
0x1800031d3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800031d7  jbe     loc_180003312
0x1800031dd  mov     [rbx+90h], r15
0x1800031e4  xorps   xmm0, xmm0
0x1800031e7  movups  xmmword ptr [rbx+70h], xmm0
0x1800031eb  movups  xmmword ptr [rbx+80h], xmm0
0x1800031f2  lea     r14, [rbx+0F8h]
0x1800031f9  mov     rax, [r14]
0x1800031fc  mov     r9d, 0FFFFFFFFh
0x180003202  xor     r8d, r8d
0x180003205  lea     rdx, qword_18002A7A0
0x18000320c  mov     rcx, r14
0x18000320f  mov     rax, [rax+20h]
0x180003213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003218  mov     esi, r15d
0x18000321b  mov     [rsp+228h+var_1F8], r15d
0x180003220  mov     edi, [r14+14h]
0x180003224  mov     rbp, r14
0x180003227  mov     [rsp+228h+var_1F0], r14
0x18000322c  mov     [rsp+228h+var_1F4], edi
0x180003230  test    edi, edi
0x180003232  jz      short loc_18000325F
0x180003234  mov     eax, esi
0x180003236  mov     rcx, [r14+8]
0x18000323a  movzx   ecx, word ptr [rcx+rax*2]
0x18000323e  call    cs:__imp__o_iswspace
0x180003244  test    eax, eax
0x180003246  jz      loc_180003443
0x18000324c  cmp     edi, 1
0x18000324f  jb      loc_180003423
0x180003255  inc     esi
0x180003257  mov     [rsp+228h+var_1F8], esi
0x18000325b  dec     edi
0x18000325d  jmp     short loc_18000322C
0x18000325f  mov     esi, r15d
0x180003262  cmp     esi, [rbx+10Ch]
0x180003268  jnz     loc_1800034A4
0x18000326e  mov     qword ptr [rbx+2ACh], 5F0000h
0x180003279  mov     [rbx+29Ah], r15
0x180003280  mov     [rbx+2A2h], r15
0x180003287  mov     [rbx+2AAh], r15w
0x18000328f  lea     rcx, [rbx+2B8h]
0x180003296  mov     rax, [rcx]
0x180003299  mov     r9d, 0FFFFFFFFh
0x18000329f  xor     r8d, r8d
0x1800032a2  lea     rdx, qword_18002A7A0
0x1800032a9  mov     rax, [rax+20h]
0x1800032ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b2  mov     [rbx+3A8h], r15
0x1800032b9  mov     [rbx+35Ch], r15d
0x1800032c0  mov     [rbx+398h], r15d
0x1800032c7  mov     rcx, [rbx+3A0h]; hMem
0x1800032ce  mov     [rbx+3A0h], r15
0x1800032d5  test    rcx, rcx
0x1800032d8  jnz     short loc_18000330A
0x1800032da  mov     word ptr [rbx+58h], 0
0x1800032e0  mov     byte ptr [rbx+5Ah], 0
0x1800032e4  mov     [rbx+5Ch], r15d
0x1800032e8  xor     eax, eax
0x1800032ea  mov     rcx, [rsp+228h+var_48]
0x1800032f2  xor     rcx, rsp; StackCookie
0x1800032f5  call    __security_check_cookie
0x1800032fa  add     rsp, 1F8h
0x180003301  pop     r15
0x180003303  pop     r14
0x180003305  pop     rdi
0x180003306  pop     rsi
0x180003307  pop     rbp
0x180003308  pop     rbx
0x180003309  retn
0x18000330a  call    cs:__imp_LocalFree
0x180003310  jmp     short loc_1800032DA
0x180003312  cmp     [rbx+90h], r15d
0x180003319  jnz     short loc_180003336
0x18000331b  mov     rsi, [rbx+60h]
0x18000331f  lea     rax, [rsi-1]
0x180003323  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003327  jbe     loc_180003405
0x18000332d  mov     [rbx+60h], r15
0x180003331  jmp     loc_1800031DD
0x180003336  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000333b  call    cs:__imp_WaitForSingleObject
0x180003341  jmp     short loc_18000331B
0x180003343  mov     rcx, [rbx+0C8h]; hEvent
0x18000334a  lea     rax, [rcx-1]
0x18000334e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180003352  ja      loc_180003157
0x180003358  call    cs:__imp_SetEvent
0x18000335e  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180003363  mov     rcx, [rbx+0D0h]; hHandle
0x18000336a  call    cs:__imp_WaitForSingleObject
0x180003370  jmp     loc_180003157
0x180003375  call    cs:__imp_GetLastError
0x18000337b  cmp     eax, 3E5h
0x180003380  jnz     loc_180003157
0x180003386  jmp     short loc_180003343
0x180003388  call    cs:__imp_GetLastError
0x18000338e  mov     edi, eax
0x180003390  mov     rcx, rbp; hObject
0x180003393  call    cs:__imp_CloseHandle
0x180003399  mov     ecx, edi; dwErrCode
0x18000339b  call    cs:__imp_SetLastError
0x1800033a1  jmp     loc_180003177
0x1800033a6  call    cs:__imp_GetLastError
0x1800033ac  mov     edi, eax
0x1800033ae  mov     rcx, rsi; hObject
0x1800033b1  call    cs:__imp_CloseHandle
0x1800033b7  mov     ecx, edi; dwErrCode
0x1800033b9  call    cs:__imp_SetLastError
0x1800033bf  jmp     loc_180003197
0x1800033c4  add     rcx, 18h
0x1800033c8  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800033cf  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800033d4  xor     edx, edx
0x1800033d6  lea     rcx, [rbx+0D8h]
0x1800033dd  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x1800033e2  jmp     loc_1800031B1
0x1800033e7  call    cs:__imp_GetLastError
0x1800033ed  mov     edi, eax
0x1800033ef  mov     rcx, rsi; hObject
0x1800033f2  call    cs:__imp_CloseHandle
0x1800033f8  mov     ecx, edi; dwErrCode
0x1800033fa  call    cs:__imp_SetLastError
0x180003400  jmp     loc_1800031C3
0x180003405  call    cs:__imp_GetLastError
0x18000340b  mov     edi, eax
0x18000340d  mov     rcx, rsi; hObject
0x180003410  call    cs:__imp_CloseHandle
0x180003416  mov     ecx, edi; dwErrCode
0x180003418  call    cs:__imp_SetLastError
0x18000341e  jmp     loc_18000332D
0x180003423  mov     rcx, [rsp+228h]; this
0x18000342b  mov     r9d, 0CEh; char *
0x180003431  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180003438  mov     edx, 39Ah; void *
0x18000343d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180003443  test    edi, edi
0x180003445  jz      loc_18000325F
0x18000344b  mov     edx, edi
0x18000344d  mov     eax, edi
0x18000344f  mov     ecx, edi
0x180003451  test    edi, edi
0x180003453  jz      short loc_180003463
0x180003455  dec     ecx
0x180003457  add     ecx, esi
0x180003459  mov     rax, [rbp+8]
0x18000345d  movzx   ecx, word ptr [rax+rcx*2]
0x180003461  jmp     short loc_180003468
0x180003463  mov     ecx, r15d
0x180003466  mov     edx, eax
0x180003468  mov     esi, edx
0x18000346a  call    cs:__imp__o_iswspace
0x180003470  test    eax, eax
0x180003472  jz      loc_180003262
0x180003478  lea     edx, [rdi-1]; unsigned int
0x18000347b  lea     rcx, [rsp+228h+var_1F8]; this
0x180003480  call    ?Truncate@CLMSubStr@@QEAAXI@Z; CLMSubStr::Truncate(uint)
0x180003485  mov     edi, [rsp+228h+var_1F4]
0x180003489  mov     edx, edi
0x18000348b  mov     eax, edi
0x18000348d  mov     esi, edi
0x18000348f  mov     ecx, edi
0x180003491  test    edi, edi
0x180003493  jz      loc_180003262
0x180003499  mov     rbp, [rsp+228h+var_1F0]
0x18000349e  mov     esi, [rsp+228h+var_1F8]
0x1800034a2  jmp     short loc_180003451
0x1800034a4  lea     rdx, [rsp+228h+var_1F8]
0x1800034a9  lea     rcx, [rsp+228h+var_1E8]
0x1800034ae  call    ??0?$TLMString@$0MA@$0EA@$0HPPP@@@QEAA@AEBVCLMSubStr@@@Z; TLMString<192,64,32767>::TLMString<192,64,32767>(CLMSubStr const &)
0x1800034b3  nop
0x1800034b4  mov     rdx, [rsp+228h+var_1E0]
0x1800034b9  mov     rcx, r14
0x1800034bc  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800034c1  nop
0x1800034c2  lea     rcx, [rsp+228h+var_1E8]
0x1800034c7  call    ??1?$TLMString@$0MA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<192,64,32767>::~TLMString<192,64,32767>(void)
0x1800034cc  jmp     loc_18000326E
```
