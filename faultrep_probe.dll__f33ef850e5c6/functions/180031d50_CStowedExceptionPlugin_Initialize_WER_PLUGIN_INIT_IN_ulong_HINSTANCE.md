# CStowedExceptionPlugin::Initialize(WER_PLUGIN_INIT_IN *,ulong,HINSTANCE__ *)

- ea: `0x180031d50`
- end: `0x180032219`
- name: `?Initialize@CStowedExceptionPlugin@@UEAAJPEAUWER_PLUGIN_INIT_IN@@KPEAUHINSTANCE__@@@Z`
- size: `1225`
- prototype: `__int64 __fastcall(CStowedExceptionPlugin *__hidden this, struct WER_PLUGIN_INIT_IN *, unsigned int, HINSTANCE)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006b50`
- `0x180009e04`
- `0x180016414`
- `0x180030e2c`
- `0x180030ff4`
- `0x180031050`
- `0x18003140c`
- `0x18003170c`
- `0x18003192c`
- `0x180031b20`
- `0x180031d50`
- `0x1800326f8`
- `0x18003e5a8`
- `0x1800492d4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031e7d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031ef0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031f26`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800321a6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031e7d`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031ef0`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x180031f26`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1800321a6`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003217a`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x18003217a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800321f9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1800321f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CStowedExceptionPlugin::Initialize(
        CStowedExceptionPlugin *this,
        struct WER_PLUGIN_INIT_IN *a2,
        __int64 a3,
        HINSTANCE a4)
{
  __int64 v6; // rcx
  unsigned int v7; // r9d
  __int64 v8; // rax
  char *v9; // r15
  unsigned int v10; // edi
  unsigned int i; // r14d
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // r9d
  int v15; // eax
  unsigned int v16; // edi
  unsigned int v17; // ecx
  void ***j; // rax
  void **v19; // rdi
  void ***k; // rax
  int v21; // eax
  _WORD *v22; // rdx
  __int64 v23; // r8
  int v24; // eax
  unsigned int v25; // r12d
  void *v26; // rdi
  SIZE_T *lpNumberOfBytesRead; // [rsp+20h] [rbp-58h]
  unsigned int v29[2]; // [rsp+30h] [rbp-48h] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-40h] BYREF
  void *Buffer; // [rsp+40h] [rbp-38h] BYREF
  void *v32[6]; // [rsp+48h] [rbp-30h] BYREF
  unsigned int v33; // [rsp+C8h] [rbp+50h] BYREF

  NumberOfBytesRead = 0;
  memset(v32, 0, 40);
  Buffer = 0;
  v33 = 0;
  v29[0] = 0;
  if ( wcscmp_0(*(const wchar_t **)a2, L"APPCRASH") && wcscmp_0(*(const wchar_t **)a2, L"MoAppCrash") )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( *((_DWORD *)a2 + 63) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_QWORD *)a2 + 38) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_DWORD *)a2 + 70) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( !*((_QWORD *)a2 + 36) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  v8 = *((_QWORD *)a2 + 36);
  if ( *(_DWORD *)v8 == -1073741189 && *(_DWORD *)(v8 + 24) == 2 )
  {
    v9 = *(char **)(v8 + 32);
    if ( v9 )
    {
      v10 = *(_DWORD *)(v8 + 40);
      if ( v10 )
      {
        *((_DWORD *)this + 68) = *((_DWORD *)a2 + 70);
        if ( v10 >= 0x100 )
          v10 = 256;
        CStowedExceptionPlugin::AddMemoryBlock(this, v9, 8 * v10, v7);
        for ( i = 0; i < v10; ++i )
        {
          if ( ReadProcessMemory(*((HANDLE *)a2 + 38), &v9[8 * i], &Buffer, 8u, &NumberOfBytesRead) )
          {
            if ( NumberOfBytesRead == 8 )
            {
              v12 = CStowedExceptionPlugin::AddBlocksForStructure(this, *((void **)a2 + 38), Buffer);
              if ( v12 < 0
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v13, Buffer, v12);
              }
            }
          }
        }
        if ( ReadProcessMemory(*((HANDLE *)a2 + 38), v9, &Buffer, 8u, &NumberOfBytesRead)
          && NumberOfBytesRead == 8
          && ReadProcessMemory(*((HANDLE *)a2 + 38), Buffer, v32, 0x28u, &NumberOfBytesRead)
          && NumberOfBytesRead == 40
          && LODWORD(v32[0]) >= 0x28
          && (unsigned int)(HIDWORD(v32[0]) - 1397043249) <= 1 )
        {
          tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
            (char *)this + 136,
            L"%08x",
            LODWORD(v32[1]));
          if ( (BYTE4(v32[1]) & 3) == 1 )
          {
            CStowedExceptionPlugin::BuildLoadedModuleList(
              (char *)this + 224,
              *((_QWORD *)a2 + 38),
              *((unsigned int *)a2 + 70));
            CStowedExceptionPlugin::BuildUnloadedModuleList((char *)this + 248, *((_QWORD *)a2 + 38));
            if ( v32[2] )
            {
              for ( j = (void ***)*((_QWORD *)this + 28); j != *((void ****)this + 29); ++j )
              {
                v19 = *j;
                if ( **j <= v32[2] && v32[2] < (char *)*v19 + *((unsigned int *)v19 + 2) )
                  goto LABEL_57;
              }
              for ( k = (void ***)*((_QWORD *)this + 31); k != *((void ****)this + 32); ++k )
              {
                v19 = *k;
                if ( **k <= v32[2] && v32[2] < (char *)*v19 + *((unsigned int *)v19 + 2) )
                {
                  v21 = 0;
                  goto LABEL_56;
                }
              }
              v19 = 0;
              v21 = -2147023728;
LABEL_56:
              if ( v21 >= 0 )
              {
LABEL_57:
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 8,
                  L"%016I64x",
                  (char *)v32[2] - (char *)*v19);
                v22 = v19[3];
                if ( v22 )
                {
                  v23 = -1;
                  do
                    ++v23;
                  while ( v22[v23] );
                }
                utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                  (char *)this + 40,
                  v22);
                if ( ((_BYTE)v19[4] & 1) != 0 )
                  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                    (char *)this + 40,
                    L"_unloaded");
                LODWORD(lpNumberOfBytesRead) = *((unsigned __int16 *)v19 + 10);
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 72,
                  L"%u.%u.%u.%u",
                  *((unsigned __int16 *)v19 + 8),
                  *((unsigned __int16 *)v19 + 9),
                  lpNumberOfBytesRead,
                  *((unsigned __int16 *)v19 + 11));
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 104,
                  L"%08x",
                  *((unsigned int *)v19 + 3));
                return 0;
              }
            }
            if ( LODWORD(v32[3]) == 8 )
            {
              v24 = HIDWORD(v32[3]);
              if ( HIDWORD(v32[3]) )
              {
                if ( v32[4] )
                {
                  if ( HIDWORD(v32[3]) > 0xFFFF )
                    v24 = 0xFFFF;
                  v25 = 8 * v24;
                  v26 = VirtualAlloc(0, (unsigned int)(8 * v24), 0x1000u, 4u);
                  *(_QWORD *)v29 = v26;
                  if ( v26
                    && ReadProcessMemory(*((HANDLE *)a2 + 38), v32[4], v26, v25, &NumberOfBytesRead)
                    && NumberOfBytesRead )
                  {
                    CStowedExceptionPlugin::HashStackTrace(&v33, (__int64)this + 248);
                    tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      (char *)this + 168,
                      L"StackHash12_%03x",
                      v33);
                  }
                  if ( v26 )
                    VirtualFree(v26, 0, 0x8000u);
                }
              }
            }
            return 0;
          }
          if ( (BYTE4(v32[1]) & 3) == 2 )
          {
            v15 = CStowedExceptionPlugin::CalculateRemoteStringLength(v29, *((void **)a2 + 38), v32[2], v14);
            if ( v15 >= 0 )
            {
              v16 = v29[0];
              if ( 2 * (unsigned __int64)v29[0] > 0xFFFF )
                MicrosoftTelemetryAssertTriggeredNoArgs(0xFFFF);
              v17 = 2 * v16;
              if ( !(2 * v16) )
                return 0;
              goto LABEL_41;
            }
            if ( v15 == -805306106 )
            {
              v17 = 0xFFFF;
LABEL_41:
              if ( (int)CStowedExceptionPlugin::HashRemoteMemory(&v33, *((HANDLE *)a2 + 38), v32[2], v17) >= 0 )
                tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 168,
                  L"TextHash12_%03x",
                  v33);
            }
          }
        }
        return 0;
      }
    }
  }
  return 2147942450LL;
}

```

## disassembly

```asm
0x180031d50  push    rbp
0x180031d52  push    rbx
0x180031d53  push    rsi
0x180031d54  push    rdi
0x180031d55  push    r12
0x180031d57  push    r13
0x180031d59  push    r14
0x180031d5b  push    r15
0x180031d5d  mov     rbp, rsp
0x180031d60  sub     rsp, 78h
0x180031d64  mov     rbx, rdx
0x180031d67  mov     rsi, rcx
0x180031d6a  xor     r13d, r13d
0x180031d6d  mov     [rbp+NumberOfBytesRead], r13
0x180031d71  mov     [rbp+var_30], r13d
0x180031d75  xorps   xmm0, xmm0
0x180031d78  xor     eax, eax
0x180031d7a  movups  xmmword ptr [rbp+var_2C], xmm0
0x180031d7e  movups  xmmword ptr [rbp+lpBaseAddress], xmm0
0x180031d82  mov     [rbp+var_C], eax
0x180031d85  mov     [rbp+Buffer], r13
0x180031d89  mov     [rbp+arg_8], r13d
0x180031d8d  mov     [rbp+var_48], r13d
0x180031d91  lea     rdx, aAppcrash; "APPCRASH"
0x180031d98  mov     rcx, [rbx]; String1
0x180031d9b  call    wcscmp_0
0x180031da0  test    eax, eax
0x180031da2  jz      short loc_180031DBC
0x180031da4  lea     rdx, aMoappcrash; "MoAppCrash"
0x180031dab  mov     rcx, [rbx]; String1
0x180031dae  call    wcscmp_0
0x180031db3  test    eax, eax
0x180031db5  jz      short loc_180031DBC
0x180031db7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031dbc  cmp     dword ptr [rbx+0FCh], 1
0x180031dc3  jz      short loc_180031DCA
0x180031dc5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031dca  cmp     [rbx+130h], r13
0x180031dd1  jnz     short loc_180031DD8
0x180031dd3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031dd8  cmp     [rbx+118h], r13d
0x180031ddf  jnz     short loc_180031DE6
0x180031de1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031de6  cmp     [rbx+120h], r13
0x180031ded  jnz     short loc_180031DF4
0x180031def  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031df4  mov     rax, [rbx+120h]
0x180031dfb  cmp     dword ptr [rax], 0C000027Bh
0x180031e01  jnz     loc_180032203
0x180031e07  cmp     dword ptr [rax+18h], 2
0x180031e0b  jnz     loc_180032203
0x180031e11  mov     r15, [rax+20h]
0x180031e15  test    r15, r15
0x180031e18  jz      loc_180032203
0x180031e1e  mov     edi, [rax+28h]
0x180031e21  test    edi, edi
0x180031e23  jz      loc_180032203
0x180031e29  mov     eax, [rbx+118h]
0x180031e2f  mov     [rsi+110h], eax
0x180031e35  mov     eax, 100h
0x180031e3a  cmp     edi, eax
0x180031e3c  cmovnb  edi, eax
0x180031e3f  lea     r8d, ds:0[rdi*8]; unsigned int
0x180031e47  mov     rdx, r15; void *
0x180031e4a  mov     rcx, rsi; this
0x180031e4d  call    ?AddMemoryBlock@CStowedExceptionPlugin@@AEAAJPEAXKK@Z; CStowedExceptionPlugin::AddMemoryBlock(void *,ulong,ulong)
0x180031e52  mov     r14d, r13d
0x180031e55  mov     r12d, 8
0x180031e5b  test    edi, edi
0x180031e5d  jz      short loc_180031ED6
0x180031e5f  mov     eax, r14d
0x180031e62  lea     rdx, [r15+rax*8]; lpBaseAddress
0x180031e66  lea     rax, [rbp+NumberOfBytesRead]
0x180031e6a  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031e6f  mov     r9, r12; nSize
0x180031e72  lea     r8, [rbp+Buffer]; lpBuffer
0x180031e76  mov     rcx, [rbx+130h]; hProcess
0x180031e7d  call    cs:__imp_ReadProcessMemory
0x180031e83  test    eax, eax
0x180031e85  jz      short loc_180031ECE
0x180031e87  cmp     [rbp+NumberOfBytesRead], r12
0x180031e8b  jnz     short loc_180031ECE
0x180031e8d  mov     r8, [rbp+Buffer]; void *
0x180031e91  mov     rdx, [rbx+130h]; void *
0x180031e98  mov     rcx, rsi; this
0x180031e9b  call    ?AddBlocksForStructure@CStowedExceptionPlugin@@AEAAJPEAX0@Z; CStowedExceptionPlugin::AddBlocksForStructure(void *,void *)
0x180031ea0  test    eax, eax
0x180031ea2  jns     short loc_180031ECE
0x180031ea4  lea     rdx, WPP_GLOBAL_Control
0x180031eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180031eb2  cmp     rcx, rdx
0x180031eb5  jz      short loc_180031ECE
0x180031eb7  test    byte ptr [rcx+1Ch], 2
0x180031ebb  jz      short loc_180031ECE
0x180031ebd  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], eax
0x180031ec1  mov     r9, [rbp+Buffer]
0x180031ec5  mov     rcx, [rcx+10h]
0x180031ec9  call    WPP_SF_qD
0x180031ece  inc     r14d
0x180031ed1  cmp     r14d, edi
0x180031ed4  jb      short loc_180031E5F
0x180031ed6  lea     rax, [rbp+NumberOfBytesRead]
0x180031eda  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031edf  mov     r9, r12; nSize
0x180031ee2  lea     r8, [rbp+Buffer]; lpBuffer
0x180031ee6  mov     rdx, r15; lpBaseAddress
0x180031ee9  mov     rcx, [rbx+130h]; hProcess
0x180031ef0  call    cs:__imp_ReadProcessMemory
0x180031ef6  test    eax, eax
0x180031ef8  jz      loc_1800321FF
0x180031efe  cmp     [rbp+NumberOfBytesRead], r12
0x180031f02  jnz     loc_1800321FF
0x180031f08  lea     rax, [rbp+NumberOfBytesRead]
0x180031f0c  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180031f11  mov     r9d, 28h ; '('; nSize
0x180031f17  lea     r8, [rbp+var_30]; lpBuffer
0x180031f1b  mov     rdx, [rbp+Buffer]; lpBaseAddress
0x180031f1f  mov     rcx, [rbx+130h]; hProcess
0x180031f26  call    cs:__imp_ReadProcessMemory
0x180031f2c  test    eax, eax
0x180031f2e  jz      loc_1800321FF
0x180031f34  cmp     [rbp+NumberOfBytesRead], 28h ; '('
0x180031f39  jnz     loc_1800321FF
0x180031f3f  cmp     [rbp+var_30], 28h ; '('
0x180031f43  jb      loc_1800321FF
0x180031f49  mov     eax, dword ptr [rbp+var_2C]
0x180031f4c  add     eax, 0ACBACFCFh
0x180031f51  cmp     eax, 1
0x180031f54  ja      loc_1800321FF
0x180031f5a  lea     rcx, [rsi+88h]
0x180031f61  mov     r8d, dword ptr [rbp+var_2C+4]
0x180031f65  lea     rdx, a08x_0; "%08x"
0x180031f6c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180031f71  mov     eax, dword ptr [rbp+var_2C+8]
0x180031f74  and     eax, 3
0x180031f77  sub     eax, 1
0x180031f7a  jz      loc_18003200B
0x180031f80  cmp     eax, 1
0x180031f83  jnz     loc_1800321FF
0x180031f89  mov     r8, [rbp+var_2C+0Ch]; void *
0x180031f8d  mov     rdx, [rbx+130h]; void *
0x180031f94  lea     rcx, [rbp+var_48]; unsigned int *
0x180031f98  call    ?CalculateRemoteStringLength@CStowedExceptionPlugin@@CAJPEAKPEAX1K@Z; CStowedExceptionPlugin::CalculateRemoteStringLength(ulong *,void *,void *,ulong)
0x180031f9d  test    eax, eax
0x180031f9f  js      short loc_180031FC5
0x180031fa1  mov     edi, [rbp+var_48]
0x180031fa4  mov     eax, edi
0x180031fa6  add     rax, rax
0x180031fa9  mov     ecx, 0FFFFh
0x180031fae  cmp     rax, rcx
0x180031fb1  jbe     short loc_180031FB8
0x180031fb3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180031fb8  lea     ecx, [rdi+rdi]
0x180031fbb  test    ecx, ecx
0x180031fbd  jz      loc_1800321FF
0x180031fc3  jmp     short loc_180031FD5
0x180031fc5  cmp     eax, 0D0000106h
0x180031fca  jnz     loc_1800321FF
0x180031fd0  mov     ecx, 0FFFFh
0x180031fd5  mov     r9d, ecx; unsigned __int64
0x180031fd8  mov     r8, [rbp+var_2C+0Ch]; void *
0x180031fdc  mov     rdx, [rbx+130h]; hProcess
0x180031fe3  lea     rcx, [rbp+arg_8]; unsigned int *
0x180031fe7  call    ?HashRemoteMemory@CStowedExceptionPlugin@@CAJPEAKPEAX1_K@Z; CStowedExceptionPlugin::HashRemoteMemory(ulong *,void *,void *,unsigned __int64)
0x180031fec  test    eax, eax
0x180031fee  js      loc_1800321FF
0x180031ff4  lea     rcx, [rsi+0A8h]
0x180031ffb  mov     r8d, [rbp+arg_8]
0x180031fff  lea     rdx, aTexthash1203x; "TextHash12_%03x"
0x180032006  jmp     loc_180032131
0x18003200b  lea     r14, [rsi+0E0h]
0x180032012  mov     r8d, [rbx+118h]
0x180032019  mov     rdx, [rbx+130h]
0x180032020  mov     rcx, r14
0x180032023  call    ?BuildLoadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAXK@Z; CStowedExceptionPlugin::BuildLoadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *,ulong)
0x180032028  lea     r15, [rsi+0F8h]
0x18003202f  mov     rdx, [rbx+130h]
0x180032036  mov     rcx, r15
0x180032039  call    ?BuildUnloadedModuleList@CStowedExceptionPlugin@@CAJPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@PEAX@Z; CStowedExceptionPlugin::BuildUnloadedModuleList(utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,void *)
0x18003203e  mov     r8, [rbp+var_2C+0Ch]
0x180032042  test    r8, r8
0x180032045  jz      loc_18003213B
0x18003204b  mov     rax, [r14]
0x18003204e  cmp     rax, [r14+8]
0x180032052  jz      short loc_18003206C
0x180032054  mov     rdi, [rax]
0x180032057  cmp     [rdi], r8
0x18003205a  ja      short loc_180032067
0x18003205c  mov     ecx, [rdi+8]
0x18003205f  add     rcx, [rdi]
0x180032062  cmp     r8, rcx
0x180032065  jb      short loc_1800320A2
0x180032067  add     rax, r12
0x18003206a  jmp     short loc_18003204E
0x18003206c  mov     rax, [r15]
0x18003206f  cmp     rax, [r15+8]
0x180032073  jz      short loc_180032092
0x180032075  mov     rdi, [rax]
0x180032078  cmp     [rdi], r8
0x18003207b  ja      short loc_180032088
0x18003207d  mov     ecx, [rdi+8]
0x180032080  add     rcx, [rdi]
0x180032083  cmp     r8, rcx
0x180032086  jb      short loc_18003208D
0x180032088  add     rax, r12
0x18003208b  jmp     short loc_18003206F
0x18003208d  mov     eax, r13d
0x180032090  jmp     short loc_18003209A
0x180032092  mov     rdi, r13
0x180032095  mov     eax, 80070490h
0x18003209a  test    eax, eax
0x18003209c  js      loc_18003213B
0x1800320a2  sub     r8, [rdi]
0x1800320a5  lea     rcx, [rsi+8]
0x1800320a9  lea     rdx, a016i64x; "%016I64x"
0x1800320b0  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800320b5  mov     rdx, [rdi+18h]
0x1800320b9  test    rdx, rdx
0x1800320bc  jz      short loc_1800320CE
0x1800320be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800320c2  inc     r8
0x1800320c5  cmp     [rdx+r8*2], r13w
0x1800320ca  jnz     short loc_1800320C2
0x1800320cc  jmp     short loc_1800320D1
0x1800320ce  mov     r8, r13
0x1800320d1  lea     rcx, [rsi+28h]
0x1800320d5  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800320da  test    byte ptr [rdi+20h], 1
0x1800320de  jz      short loc_1800320F6
0x1800320e0  mov     r8d, 9
0x1800320e6  lea     rdx, SubStr; "_unloaded"
0x1800320ed  lea     rcx, [rsi+28h]
0x1800320f1  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1800320f6  movzx   eax, word ptr [rdi+16h]
0x1800320fa  movzx   r10d, word ptr [rdi+14h]
0x1800320ff  movzx   r9d, word ptr [rdi+12h]
0x180032104  movzx   r8d, word ptr [rdi+10h]
0x180032109  lea     rcx, [rsi+48h]
0x18003210d  mov     [rsp+78h+var_50], eax
0x180032111  mov     dword ptr [rsp+78h+lpNumberOfBytesRead], r10d
0x180032116  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x18003211d  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180032122  lea     rcx, [rsi+68h]
0x180032126  mov     r8d, [rdi+0Ch]
0x18003212a  lea     rdx, a08x_0; "%08x"
0x180032131  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180032136  jmp     loc_1800321FF
0x18003213b  cmp     dword ptr [rbp+lpBaseAddress+4], r12d
0x18003213f  jnz     loc_1800321FF
0x180032145  mov     eax, dword ptr [rbp+lpBaseAddress+8]
0x180032148  test    eax, eax
0x18003214a  jz      loc_1800321FF
0x180032150  cmp     [rbp+lpBaseAddress+0Ch], r13
0x180032154  jz      loc_1800321FF
0x18003215a  mov     ecx, 0FFFFh
0x18003215f  cmp     eax, ecx
0x180032161  cmova   eax, ecx
0x180032164  shl     eax, 3
0x180032167  mov     r12d, eax
0x18003216a  mov     r9d, 4; flProtect
0x180032170  mov     r8d, 1000h; flAllocationType
0x180032176  mov     edx, eax; dwSize
0x180032178  xor     ecx, ecx; lpAddress
0x18003217a  call    cs:__imp_VirtualAlloc
0x180032180  mov     rdi, rax
0x180032183  mov     qword ptr [rbp+var_48], rax
0x180032187  test    rax, rax
0x18003218a  jz      short loc_1800321E9
0x18003218c  lea     rax, [rbp+NumberOfBytesRead]
0x180032190  mov     [rsp+78h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x180032195  mov     r9d, r12d; nSize
0x180032198  mov     r8, rdi; lpBuffer
0x18003219b  mov     rdx, [rbp+lpBaseAddress+0Ch]; lpBaseAddress
0x18003219f  mov     rcx, [rbx+130h]; hProcess
0x1800321a6  call    cs:__imp_ReadProcessMemory
0x1800321ac  test    eax, eax
0x1800321ae  jz      short loc_1800321E9
0x1800321b0  mov     rdx, [rbp+NumberOfBytesRead]
0x1800321b4  test    rdx, rdx
0x1800321b7  jz      short loc_1800321E9
0x1800321b9  shr     rdx, 3
0x1800321bd  mov     [rsp+78h+lpNumberOfBytesRead], r15; __int64
0x1800321c2  mov     r9, r14
0x1800321c5  mov     r8, rdi
0x1800321c8  lea     rcx, [rbp+arg_8]; unsigned int *
0x1800321cc  call    ?HashStackTrace@CStowedExceptionPlugin@@CAJPEAKKPEAPEAXPEAV?$vector@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@V?$allocator@V?$unique_ptr@UPROCESS_MODULE@@U?$generic_delete@UPROCESS_MODULE@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@2@@utl@@2@Z; CStowedExceptionPlugin::HashStackTrace(ulong *,ulong,void * *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *,utl::vector<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>,utl::allocator<utl::unique_ptr<PROCESS_MODULE,tlx::generic_delete<PROCESS_MODULE,tlx::operator_delete_deallocate>>>> *)
0x1800321d1  lea     rcx, [rsi+0A8h]
0x1800321d8  mov     r8d, [rbp+arg_8]
0x1800321dc  lea     rdx, aStackhash1203x; "StackHash12_%03x"
0x1800321e3  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800321e8  nop
0x1800321e9  test    rdi, rdi
0x1800321ec  jz      short loc_1800321FF
0x1800321ee  xor     edx, edx; dwSize
0x1800321f0  mov     r8d, 8000h; dwFreeType
0x1800321f6  mov     rcx, rdi; lpAddress
0x1800321f9  call    cs:__imp_VirtualFree
0x1800321ff  xor     eax, eax
0x180032201  jmp     short loc_180032208
0x180032203  mov     eax, 80070032h
  ... truncated ...
```
