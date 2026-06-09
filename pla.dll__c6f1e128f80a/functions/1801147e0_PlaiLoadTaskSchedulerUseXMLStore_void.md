# PlaiLoadTaskSchedulerUseXMLStore(void)

- ea: `0x1801147e0`
- end: `0x180114a2b`
- name: `?PlaiLoadTaskSchedulerUseXMLStore@@YAJXZ`
- size: `587`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b33c`
- `0x18012c5f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1801147e0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180114834`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180114834`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180114a08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180114a08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011494e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18011494e`

## string_xrefs

- `0x18011481b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Schedule\Configuration`
- `0x1801148c6`: `PlaiLoadTaskSchedulerUseXMLStore`
- `0x1801149d3`: `PlaiLoadTaskSchedulerUseXMLStore`
- `0x180114944`: `UseXmlStore`

## pseudocode

```c
__int64 PlaiLoadTaskSchedulerUseXMLStore(void)
{
  LSTATUS v0; // eax
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rax
  LSTATUS v4; // eax
  int v5; // eax
  __int64 v6; // rax
  int v8; // [rsp+70h] [rbp-90h] BYREF
  int v9; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[4]; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD Type; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v14[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v15[64]; // [rsp+120h] [rbp+20h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Schedule\\Configuration",
         0,
         0x20019u,
         &hKey);
  v1 = PlaiHResultFromWin32(v0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    cbData = 4;
    v4 = RegQueryValueExW(hKey, L"UseXmlStore", 0, &Type, Data, &cbData);
    v5 = PlaiHResultFromWin32(v4);
    v2 = v5;
    if ( v5 >= 0 )
    {
      if ( *(_DWORD *)Data == 1 )
        g_isTaskSchedulerUseXMLStoreEnabled = 1;
    }
    else
    {
      v9 = 0;
      v8 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v15, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v15[v6] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v8,
          4,
          qword_180147320,
          1,
          &v9,
          4,
          "PlaiLoadTaskSchedulerUseXMLStore",
          33);
      }
    }
  }
  else
  {
    v8 = 0;
    v9 = v1;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v14, 0x4000000000000800uLL);
      v3 = -1;
      do
        ++v3;
      while ( v14[v3] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v9,
        4,
        qword_180147320,
        1,
        &v8,
        4,
        "PlaiLoadTaskSchedulerUseXMLStore",
        33);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1801147e0  push    rbp
0x1801147e2  push    rbx
0x1801147e3  push    rsi
0x1801147e4  push    rdi
0x1801147e5  lea     rbp, [rsp-0B8h]
0x1801147ed  sub     rsp, 1B8h
0x1801147f4  mov     rax, cs:__security_cookie
0x1801147fb  xor     rax, rsp
0x1801147fe  mov     [rbp+0D0h+var_30], rax
0x180114805  xor     esi, esi
0x180114807  lea     rax, [rbp+0D0h+hKey]
0x18011480b  mov     r9d, 20019h; samDesired
0x180114811  mov     [rbp+0D0h+hKey], rsi
0x180114815  xor     r8d, r8d; ulOptions
0x180114818  mov     dword ptr [rbp+0D0h+Data], esi
0x18011481b  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180114822  mov     [rbp+0D0h+cbData], esi
0x180114825  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011482c  mov     [rbp+0D0h+Type], esi
0x18011482f  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180114834  call    cs:__imp_RegOpenKeyExW
0x18011483a  mov     ecx, eax; unsigned int
0x18011483c  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180114841  mov     ebx, eax
0x180114843  test    eax, eax
0x180114845  jns     loc_180114922
0x18011484b  cmp     dword ptr cs:xmmword_180169738, esi
0x180114851  mov     [rsp+1D0h+var_160], esi
0x180114855  mov     [rsp+1D0h+var_158], eax
0x180114859  jz      loc_1801149FF
0x18011485f  mov     rdx, 4000000000000800h; unsigned __int64
0x180114869  test    qword ptr cs:xmmword_180169738+8, rdx
0x180114870  jz      loc_1801149FF
0x180114876  mov     rax, cs:qword_180169748
0x18011487d  and     rax, rdx
0x180114880  cmp     cs:qword_180169748, rax
0x180114887  jnz     loc_1801149FF
0x18011488d  lea     rcx, [rbp+0D0h+var_130]; unsigned __int16 *
0x180114891  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180114896  lea     rcx, [rbp+0D0h+var_130]
0x18011489a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18011489e  inc     rax
0x1801148a1  cmp     [rcx+rax*2], si
0x1801148a5  jnz     short loc_18011489E
0x1801148a7  lea     ecx, [rax+rax]
0x1801148aa  mov     edi, 4
0x1801148af  lea     rax, [rbp+0D0h+var_130]
0x1801148b3  add     rcx, 2
0x1801148b7  mov     [rsp+1D0h+var_170], rcx
0x1801148bc  lea     r9, [rsp+1D0h+var_158]
0x1801148c1  mov     [rsp+1D0h+var_178], rax
0x1801148c6  lea     rax, aPlailoadtasksc; "PlaiLoadTaskSchedulerUseXMLStore"
0x1801148cd  mov     [rsp+1D0h+var_180], 21h ; '!'
0x1801148d6  mov     [rsp+1D0h+var_188], rax
0x1801148db  lea     rax, [rsp+1D0h+var_160]
0x1801148e0  mov     [rsp+1D0h+var_190], rdi
0x1801148e5  lea     rdx, PLA_EVENT_ERROR
0x1801148ec  mov     [rsp+1D0h+var_198], rax
0x1801148f1  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801148f8  lea     rax, qword_180147320
0x1801148ff  mov     [rsp+1D0h+var_1A0], 1
0x180114908  mov     [rsp+1D0h+lpcbData], rax
0x18011490d  mov     r8d, 5
0x180114913  mov     [rsp+1D0h+phkResult], rdi
0x180114918  call    EventingWriteEvent
0x18011491d  jmp     loc_1801149FF
0x180114922  mov     rcx, [rbp+0D0h+hKey]; hKey
0x180114926  lea     rax, [rbp+0D0h+cbData]
0x18011492a  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x18011492f  lea     r9, [rbp+0D0h+Type]; lpType
0x180114933  lea     rax, [rbp+0D0h+Data]
0x180114937  mov     edi, 4
0x18011493c  xor     r8d, r8d; lpReserved
0x18011493f  mov     [rsp+1D0h+phkResult], rax; lpData
0x180114944  lea     rdx, aUsexmlstore; "UseXmlStore"
0x18011494b  mov     [rbp+0D0h+cbData], edi
0x18011494e  call    cs:__imp_RegQueryValueExW
0x180114954  mov     ecx, eax; unsigned int
0x180114956  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18011495b  mov     ebx, eax
0x18011495d  test    eax, eax
0x18011495f  jns     loc_1801149F2
0x180114965  cmp     dword ptr cs:xmmword_180169738, esi
0x18011496b  mov     [rsp+1D0h+var_158], esi
0x18011496f  mov     [rsp+1D0h+var_160], eax
0x180114973  jz      loc_1801149FF
0x180114979  mov     rdx, 4000000000000800h; unsigned __int64
0x180114983  test    qword ptr cs:xmmword_180169738+8, rdx
0x18011498a  jz      short loc_1801149FF
0x18011498c  mov     rax, cs:qword_180169748
0x180114993  and     rax, rdx
0x180114996  cmp     cs:qword_180169748, rax
0x18011499d  jnz     short loc_1801149FF
0x18011499f  lea     rcx, [rbp+0D0h+var_B0]; unsigned __int16 *
0x1801149a3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801149a8  lea     rcx, [rbp+0D0h+var_B0]
0x1801149ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801149b0  inc     rax
0x1801149b3  cmp     [rcx+rax*2], si
0x1801149b7  jnz     short loc_1801149B0
0x1801149b9  lea     ecx, [rax+rax]
0x1801149bc  lea     rax, [rbp+0D0h+var_B0]
0x1801149c0  add     rcx, 2
0x1801149c4  mov     [rsp+1D0h+var_170], rcx
0x1801149c9  lea     r9, [rsp+1D0h+var_160]
0x1801149ce  mov     [rsp+1D0h+var_178], rax
0x1801149d3  lea     rax, aPlailoadtasksc; "PlaiLoadTaskSchedulerUseXMLStore"
0x1801149da  mov     [rsp+1D0h+var_180], 21h ; '!'
0x1801149e3  mov     [rsp+1D0h+var_188], rax
0x1801149e8  lea     rax, [rsp+1D0h+var_158]
0x1801149ed  jmp     loc_1801148E0
0x1801149f2  cmp     dword ptr [rbp+0D0h+Data], 1
0x1801149f6  jnz     short loc_1801149FF
0x1801149f8  mov     cs:?g_isTaskSchedulerUseXMLStoreEnabled@@3_NA, 1; bool g_isTaskSchedulerUseXMLStoreEnabled
0x1801149ff  mov     rcx, [rbp+0D0h+hKey]; hKey
0x180114a03  test    rcx, rcx
0x180114a06  jz      short loc_180114A0E
0x180114a08  call    cs:__imp_RegCloseKey
0x180114a0e  mov     eax, ebx
0x180114a10  mov     rcx, [rbp+0D0h+var_30]
0x180114a17  xor     rcx, rsp; StackCookie
0x180114a1a  call    __security_check_cookie
0x180114a1f  add     rsp, 1B8h
0x180114a26  pop     rdi
0x180114a27  pop     rsi
0x180114a28  pop     rbx
0x180114a29  pop     rbp
0x180114a2a  retn
```
