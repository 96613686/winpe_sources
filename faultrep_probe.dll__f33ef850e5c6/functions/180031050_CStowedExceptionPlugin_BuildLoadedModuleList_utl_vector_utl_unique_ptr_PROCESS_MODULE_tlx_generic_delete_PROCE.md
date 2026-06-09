# CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)

- ea: `0x180031050`
- end: `0x180031404`
- name: `?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z`
- size: `948`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031d50`

## callees

- `0x180002890`
- `0x1800028ec`
- `0x180002e90`
- `0x180003474`
- `0x180031050`
- `0x180032650`
- `0x18003a164`
- `0x18003ae98`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180031295`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180031295`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800310c2`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800310c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800313b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031394`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800313b1`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800310da`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1800310da`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180031374`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180031374`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18003118a`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18003118a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall CStowedExceptionPlugin::BuildLoadedModuleList(__int64 a1, void *a2, DWORD a3)
{
  __int64 v6; // rcx
  HANDLE Toolhelp32Snapshot; // r14
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  WCHAR *szModule; // rax
  unsigned __int64 v13; // rdi
  _OWORD *v14; // rbx
  __int16 v15; // cx
  __int16 v16; // cx
  unsigned __int64 i; // rsi
  void *v18; // rbx
  MODULEENTRY32W *v19; // rdx
  _OWORD *v20; // rax
  __int64 v21; // rcx
  BOOL v22; // edi
  signed int result; // eax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h]
  __int128 v26; // [rsp+48h] [rbp-B8h]
  __int128 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+68h] [rbp-98h]
  _BYTE v29[1088]; // [rsp+70h] [rbp-90h] BYREF
  MODULEENTRY32W me; // [rsp+4B0h] [rbp+3B0h] BYREF

  memset_0(&me, 0, sizeof(me));
  Block = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( a3 != GetProcessId(a2) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, a3);
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 > 1 )
  {
    memset_0(v29, 0, 0x438u);
    p_me = &me;
    v9 = v29;
    v10 = 8;
    do
    {
      *(_OWORD *)&p_me->dwSize = *v9;
      *(_OWORD *)&p_me->ProccntUsage = v9[1];
      *(_OWORD *)&p_me->modBaseSize = v9[2];
      *(_OWORD *)p_me->szModule = v9[3];
      *(_OWORD *)&p_me->szModule[8] = v9[4];
      *(_OWORD *)&p_me->szModule[16] = v9[5];
      *(_OWORD *)&p_me->szModule[24] = v9[6];
      *(_OWORD *)&p_me->szModule[32] = v9[7];
      p_me = (MODULEENTRY32W *)((char *)p_me + 128);
      v9 += 8;
      --v10;
    }
    while ( v10 );
    *(_OWORD *)&p_me->dwSize = *v9;
    *(_OWORD *)&p_me->ProccntUsage = v9[1];
    *(_OWORD *)&p_me->modBaseSize = v9[2];
    *(_QWORD *)p_me->szModule = *((_QWORD *)v9 + 6);
    me.dwSize = 1080;
    if ( !Module32FirstW(Toolhelp32Snapshot, &me) )
    {
LABEL_25:
      CloseHandle(Toolhelp32Snapshot);
      return 0;
    }
    while ( 1 )
    {
      v11 = 256;
      szModule = me.szModule;
      do
      {
        if ( !*szModule )
          break;
        ++szModule;
        --v11;
      }
      while ( v11 );
      v13 = (256 - v11) & -(__int64)(v11 != 0);
      if ( !v11 )
      {
        v13 = 255;
        me.szModule[255] = 0;
      }
      v14 = operator new((unsigned int)(2 * v13 + 2) + 40LL, (const struct std::nothrow_t *)&std::nothrow);
      if ( v14 )
      {
        *v14 = 0;
        v14[1] = 0;
        *((_QWORD *)v14 + 4) = 0;
        Block = v14;
        *(_QWORD *)v14 = me.modBaseAddr;
        *((_DWORD *)v14 + 2) = me.modBaseSize;
        *((_DWORD *)v14 + 3) = UtilGetTimestampModule(a2, (HINSTANCE)me.modBaseAddr);
        if ( (int)UtilGetFileInfo(me.szExePath, 0) >= 0 )
        {
          v15 = WORD4(v25);
          *((_WORD *)v14 + 8) = WORD5(v25);
          *((_WORD *)v14 + 9) = v15;
          v16 = WORD6(v25);
          *((_WORD *)v14 + 10) = HIWORD(v25);
          *((_WORD *)v14 + 11) = v16;
        }
        *((_QWORD *)v14 + 3) = (char *)v14 + 40;
        *((_DWORD *)v14 + 8) = 0;
        for ( i = 0; i < v13; ++i )
          *(_WORD *)(*((_QWORD *)v14 + 3) + 2 * i) = _o_towlower(me.szModule[i]);
        *(_WORD *)(*((_QWORD *)v14 + 3) + 2 * v13) = 0;
        if ( !(unsigned __int8)utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(
                                 a1,
                                 &Block) )
        {
          if ( Block )
            operator delete(Block);
          CloseHandle(Toolhelp32Snapshot);
          return -2147024882;
        }
        v18 = Block;
      }
      else
      {
        v18 = 0;
      }
      memset_0(v29, 0, 0x438u);
      v19 = &me;
      v20 = v29;
      v21 = 8;
      do
      {
        *(_OWORD *)&v19->dwSize = *v20;
        *(_OWORD *)&v19->ProccntUsage = v20[1];
        *(_OWORD *)&v19->modBaseSize = v20[2];
        *(_OWORD *)v19->szModule = v20[3];
        *(_OWORD *)&v19->szModule[8] = v20[4];
        *(_OWORD *)&v19->szModule[16] = v20[5];
        *(_OWORD *)&v19->szModule[24] = v20[6];
        *(_OWORD *)&v19->szModule[32] = v20[7];
        v19 = (MODULEENTRY32W *)((char *)v19 + 128);
        v20 += 8;
        --v21;
      }
      while ( v21 );
      *(_OWORD *)&v19->dwSize = *v20;
      *(_OWORD *)&v19->ProccntUsage = v20[1];
      *(_OWORD *)&v19->modBaseSize = v20[2];
      *(_QWORD *)v19->szModule = *((_QWORD *)v20 + 6);
      me.dwSize = 1080;
      v22 = Module32NextW(Toolhelp32Snapshot, &me);
      if ( v18 )
        operator delete(v18);
      if ( !v22 )
        goto LABEL_25;
    }
  }
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x180031050  mov     [rsp-8+arg_18], rbx
0x180031055  push    rbp
0x180031056  push    rsi
0x180031057  push    rdi
0x180031058  push    r12
0x18003105a  push    r13
0x18003105c  push    r14
0x18003105e  push    r15
0x180031060  lea     rbp, [rsp-800h]
0x180031068  sub     rsp, 900h
0x18003106f  mov     rax, cs:__security_cookie
0x180031076  xor     rax, rsp
0x180031079  mov     [rbp+830h+var_40], rax
0x180031080  mov     ebx, r8d
0x180031083  mov     r15, rdx
0x180031086  mov     r12, rcx
0x180031089  mov     esi, 438h
0x18003108e  mov     r8d, esi; Size
0x180031091  xor     edx, edx; Val
0x180031093  lea     rcx, [rbp+830h+me]; void *
0x18003109a  call    memset_0
0x18003109f  xor     r13d, r13d
0x1800310a2  mov     [rsp+930h+Block], r13
0x1800310a7  xorps   xmm0, xmm0
0x1800310aa  xor     eax, eax
0x1800310ac  movups  [rsp+930h+var_8F8], xmm0
0x1800310b1  movups  [rsp+930h+var_8E8], xmm0
0x1800310b6  movups  [rsp+930h+var_8D8], xmm0
0x1800310bb  mov     [rsp+930h+var_8C8], eax
0x1800310bf  mov     rcx, r15; Process
0x1800310c2  call    cs:__imp_GetProcessId
0x1800310c8  cmp     ebx, eax
0x1800310ca  jz      short loc_1800310D1
0x1800310cc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800310d1  mov     edx, ebx; th32ProcessID
0x1800310d3  mov     ebx, 8
0x1800310d8  mov     ecx, ebx; dwFlags
0x1800310da  call    cs:__imp_CreateToolhelp32Snapshot
0x1800310e0  mov     r14, rax
0x1800310e3  lea     rcx, [rax+1]
0x1800310e7  cmp     rcx, 1
0x1800310eb  jbe     loc_1800313BE
0x1800310f1  mov     r8, rsi; Size
0x1800310f4  xor     edx, edx; Val
0x1800310f6  lea     rcx, [rsp+930h+var_8C0]; void *
0x1800310fb  call    memset_0
0x180031100  lea     rcx, [rbp+830h+me]
0x180031107  lea     rax, [rsp+930h+var_8C0]
0x18003110c  mov     edx, ebx
0x18003110e  lea     r8d, [rbx+78h]
0x180031112  movups  xmm0, xmmword ptr [rax]
0x180031115  movups  xmmword ptr [rcx], xmm0
0x180031118  movups  xmm1, xmmword ptr [rax+10h]
0x18003111c  movups  xmmword ptr [rcx+10h], xmm1
0x180031120  movups  xmm0, xmmword ptr [rax+20h]
0x180031124  movups  xmmword ptr [rcx+20h], xmm0
0x180031128  movups  xmm1, xmmword ptr [rax+30h]
0x18003112c  movups  xmmword ptr [rcx+30h], xmm1
0x180031130  movups  xmm0, xmmword ptr [rax+40h]
0x180031134  movups  xmmword ptr [rcx+40h], xmm0
0x180031138  movups  xmm1, xmmword ptr [rax+50h]
0x18003113c  movups  xmmword ptr [rcx+50h], xmm1
0x180031140  movups  xmm0, xmmword ptr [rax+60h]
0x180031144  movups  xmmword ptr [rcx+60h], xmm0
0x180031148  movups  xmm1, xmmword ptr [rax+70h]
0x18003114c  movups  xmmword ptr [rcx+70h], xmm1
0x180031150  add     rcx, r8
0x180031153  add     rax, r8
0x180031156  sub     rdx, 1
0x18003115a  jnz     short loc_180031112
0x18003115c  movups  xmm0, xmmword ptr [rax]
0x18003115f  movups  xmmword ptr [rcx], xmm0
0x180031162  movups  xmm1, xmmword ptr [rax+10h]
0x180031166  movups  xmmword ptr [rcx+10h], xmm1
0x18003116a  movups  xmm0, xmmword ptr [rax+20h]
0x18003116e  movups  xmmword ptr [rcx+20h], xmm0
0x180031172  mov     rax, [rax+30h]
0x180031176  mov     [rcx+30h], rax
0x18003117a  mov     [rbp+830h+me.dwSize], esi
0x180031180  lea     rdx, [rbp+830h+me]; lpme
0x180031187  mov     rcx, r14; hSnapshot
0x18003118a  call    cs:__imp_Module32FirstW
0x180031190  test    eax, eax
0x180031192  jz      loc_180031391
0x180031198  mov     edx, 100h
0x18003119d  lea     rax, [rbp+830h+me.szModule]
0x1800311a4  cmp     [rax], r13w
0x1800311a8  jz      short loc_1800311B4
0x1800311aa  add     rax, 2
0x1800311ae  sub     rdx, 1
0x1800311b2  jnz     short loc_1800311A4
0x1800311b4  mov     rax, rdx
0x1800311b7  mov     ecx, 100h
0x1800311bc  sub     rcx, rdx
0x1800311bf  neg     rax
0x1800311c2  sbb     rdi, rdi
0x1800311c5  and     rdi, rcx
0x1800311c8  test    rdx, rdx
0x1800311cb  jnz     short loc_1800311DA
0x1800311cd  mov     edi, 0FFh
0x1800311d2  mov     [rbp+830h+me.szModule+1FEh], r13w
0x1800311da  lea     ecx, ds:2[rdi*2]
0x1800311e1  add     rcx, 28h ; '('; unsigned __int64
0x1800311e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800311ec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800311f1  mov     rbx, rax
0x1800311f4  test    rax, rax
0x1800311f7  jz      loc_1800312D5
0x1800311fd  xorps   xmm0, xmm0
0x180031200  xor     eax, eax
0x180031202  movups  xmmword ptr [rbx], xmm0
0x180031205  movups  xmmword ptr [rbx+10h], xmm0
0x180031209  mov     [rbx+20h], rax
0x18003120d  mov     [rsp+930h+Block], rbx
0x180031212  mov     rcx, [rbp+830h+me.modBaseAddr]
0x180031219  mov     [rbx], rcx
0x18003121c  mov     ecx, [rbp+830h+me.modBaseSize]
0x180031222  mov     [rbx+8], ecx
0x180031225  mov     rdx, [rbp+830h+me.modBaseAddr]; lpBaseAddress
0x18003122c  mov     rcx, r15; hProcess
0x18003122f  call    ?UtilGetTimestampModule@@YAKPEAXPEAUHINSTANCE__@@@Z; UtilGetTimestampModule(void *,HINSTANCE__ *)
0x180031234  mov     [rbx+0Ch], eax
0x180031237  mov     [rsp+930h+var_910], r13d; int
0x18003123c  xor     r9d, r9d
0x18003123f  xor     r8d, r8d
0x180031242  lea     rdx, [rsp+930h+var_8F8]
0x180031247  lea     rcx, [rbp+830h+me.szExePath]; lpwstrFilename
0x18003124e  call    ?UtilGetFileInfo@@YAJPEB_WPEAUtagVS_FIXEDFILEINFO@@QEBQEB_WQEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@K@Z; UtilGetFileInfo(wchar_t const *,tagVS_FIXEDFILEINFO *,wchar_t const * const * const,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> * const,ulong)
0x180031253  test    eax, eax
0x180031255  js      short loc_180031279
0x180031257  mov     ecx, dword ptr [rsp+930h+var_8F8+8]
0x18003125b  mov     eax, ecx
0x18003125d  shr     eax, 10h
0x180031260  mov     [rbx+10h], ax
0x180031264  mov     [rbx+12h], cx
0x180031268  mov     ecx, dword ptr [rsp+930h+var_8F8+0Ch]
0x18003126c  mov     eax, ecx
0x18003126e  shr     eax, 10h
0x180031271  mov     [rbx+14h], ax
0x180031275  mov     [rbx+16h], cx
0x180031279  lea     rax, [rbx+28h]
0x18003127d  mov     [rbx+18h], rax
0x180031281  mov     [rbx+20h], r13d
0x180031285  mov     rsi, r13
0x180031288  test    rdi, rdi
0x18003128b  jz      short loc_1800312AB
0x18003128d  movzx   ecx, [rbp+rsi*2+830h+me.szModule]
0x180031295  call    cs:__imp__o_towlower
0x18003129b  mov     rcx, [rbx+18h]
0x18003129f  mov     [rcx+rsi*2], ax
0x1800312a3  inc     rsi
0x1800312a6  cmp     rsi, rdi
0x1800312a9  jb      short loc_18003128D
0x1800312ab  mov     rcx, [rbx+18h]
0x1800312af  mov     [rcx+rdi*2], r13w
0x1800312b4  lea     rdx, [rsp+930h+Block]
0x1800312b9  mov     rcx, r12
0x1800312bc  call    ?push_back@?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@2@@Z; utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>>::push_back(utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>> &&)
0x1800312c1  test    al, al
0x1800312c3  jz      loc_18003139E
0x1800312c9  mov     rbx, [rsp+930h+Block]
0x1800312ce  mov     esi, 438h
0x1800312d3  jmp     short loc_1800312D8
0x1800312d5  mov     rbx, r13
0x1800312d8  mov     r8, rsi; Size
0x1800312db  xor     edx, edx; Val
0x1800312dd  lea     rcx, [rsp+930h+var_8C0]; void *
0x1800312e2  call    memset_0
0x1800312e7  lea     rdx, [rbp+830h+me]
0x1800312ee  lea     rax, [rsp+930h+var_8C0]
0x1800312f3  mov     ecx, 8
0x1800312f8  lea     r8d, [rcx+78h]
0x1800312fc  movups  xmm0, xmmword ptr [rax]
0x1800312ff  movups  xmmword ptr [rdx], xmm0
0x180031302  movups  xmm1, xmmword ptr [rax+10h]
0x180031306  movups  xmmword ptr [rdx+10h], xmm1
0x18003130a  movups  xmm0, xmmword ptr [rax+20h]
0x18003130e  movups  xmmword ptr [rdx+20h], xmm0
0x180031312  movups  xmm1, xmmword ptr [rax+30h]
0x180031316  movups  xmmword ptr [rdx+30h], xmm1
0x18003131a  movups  xmm0, xmmword ptr [rax+40h]
0x18003131e  movups  xmmword ptr [rdx+40h], xmm0
0x180031322  movups  xmm1, xmmword ptr [rax+50h]
0x180031326  movups  xmmword ptr [rdx+50h], xmm1
0x18003132a  movups  xmm0, xmmword ptr [rax+60h]
0x18003132e  movups  xmmword ptr [rdx+60h], xmm0
0x180031332  movups  xmm1, xmmword ptr [rax+70h]
0x180031336  movups  xmmword ptr [rdx+70h], xmm1
0x18003133a  add     rdx, r8
0x18003133d  add     rax, r8
0x180031340  sub     rcx, 1
0x180031344  jnz     short loc_1800312FC
0x180031346  movups  xmm0, xmmword ptr [rax]
0x180031349  movups  xmmword ptr [rdx], xmm0
0x18003134c  movups  xmm1, xmmword ptr [rax+10h]
0x180031350  movups  xmmword ptr [rdx+10h], xmm1
0x180031354  movups  xmm0, xmmword ptr [rax+20h]
0x180031358  movups  xmmword ptr [rdx+20h], xmm0
0x18003135c  mov     rax, [rax+30h]
0x180031360  mov     [rdx+30h], rax
0x180031364  mov     [rbp+830h+me.dwSize], esi
0x18003136a  lea     rdx, [rbp+830h+me]; lpme
0x180031371  mov     rcx, r14; hSnapshot
0x180031374  call    cs:__imp_Module32NextW
0x18003137a  mov     edi, eax
0x18003137c  test    rbx, rbx
0x18003137f  jz      short loc_180031389
0x180031381  mov     rcx, rbx; Block
0x180031384  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031389  test    edi, edi
0x18003138b  jnz     loc_180031198
0x180031391  mov     rcx, r14; hObject
0x180031394  call    cs:__imp_CloseHandle
0x18003139a  xor     eax, eax
0x18003139c  jmp     short loc_1800313DA
0x18003139e  mov     rcx, [rsp+930h+Block]; Block
0x1800313a3  test    rcx, rcx
0x1800313a6  jz      short loc_1800313AE
0x1800313a8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800313ad  nop
0x1800313ae  mov     rcx, r14; hObject
0x1800313b1  call    cs:__imp_CloseHandle
0x1800313b7  mov     eax, 8007000Eh
0x1800313bc  jmp     short loc_1800313DA
0x1800313be  call    cs:__imp_GetLastError
0x1800313c4  test    eax, eax
0x1800313c6  jle     short loc_1800313D0
0x1800313c8  movzx   eax, ax
0x1800313cb  or      eax, 80070000h
0x1800313d0  mov     ecx, 80004005h
0x1800313d5  test    eax, eax
0x1800313d7  cmovns  eax, ecx
0x1800313da  mov     rcx, [rbp+830h+var_40]
0x1800313e1  xor     rcx, rsp; StackCookie
0x1800313e4  call    __security_check_cookie
0x1800313e9  mov     rbx, [rsp+930h+arg_18]
0x1800313f1  add     rsp, 900h
0x1800313f8  pop     r15
0x1800313fa  pop     r14
0x1800313fc  pop     r13
0x1800313fe  pop     r12
0x180031400  pop     rdi
0x180031401  pop     rsi
0x180031402  pop     rbp
0x180031403  retn
```
