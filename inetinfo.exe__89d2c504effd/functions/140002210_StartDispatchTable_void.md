# StartDispatchTable(void)

- ea: `0x140002210`
- end: `0x1400024c7`
- name: `?StartDispatchTable@@YAXXZ`
- size: `695`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1400024d0`

## callees

- `0x140002210`
- `0x140002850`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x1400022af`
- `ADVAPI32!RegQueryValueExA` at `0x140002305`
- `ADVAPI32!RegQueryValueExA` at `0x1400022af`
- `ADVAPI32!RegQueryValueExA` at `0x140002305`
- `ADVAPI32!StartServiceCtrlDispatcherA` at `0x140002431`
- `ADVAPI32!StartServiceCtrlDispatcherA` at `0x140002431`
- `ADVAPI32!RegCloseKey` at `0x140002428`
- `ADVAPI32!RegCloseKey` at `0x140002428`
- `ADVAPI32!RegOpenKeyExA` at `0x140002273`
- `ADVAPI32!RegOpenKeyExA` at `0x140002273`
- `KERNEL32!LocalAlloc` at `0x1400022d0`
- `KERNEL32!LocalAlloc` at `0x140002380`
- `KERNEL32!LocalAlloc` at `0x1400022d0`
- `KERNEL32!LocalAlloc` at `0x140002380`
- `KERNEL32!GetLastError` at `0x14000243b`
- `KERNEL32!GetLastError` at `0x14000243b`
- `KERNEL32!LocalFree` at `0x140002415`
- `KERNEL32!LocalFree` at `0x140002497`
- `KERNEL32!LocalFree` at `0x1400024a5`
- `KERNEL32!LocalFree` at `0x140002415`
- `KERNEL32!LocalFree` at `0x140002497`
- `KERNEL32!LocalFree` at `0x1400024a5`
- `msvcrt!sprintf_s` at `0x140002455`
- `msvcrt!sprintf_s` at `0x140002455`
- `iisutil!PuDbgPrint` at `0x140002489`
- `iisutil!PuDbgPrint` at `0x140002489`

## string_xrefs

- `0x14000225a`: `System\CurrentControlSet\Services\InetInfo\Parameters`

## pseudocode

```c
void StartDispatchTable(void)
{
  SERVICE_TABLE_ENTRYA *v0; // rsi
  BYTE *v1; // rbx
  unsigned int v2; // edi
  int v3; // r8d
  BYTE *v4; // r9
  DWORD v5; // r10d
  bool v6; // zf
  DWORD v7; // edx
  BYTE v8; // cl
  int v9; // eax
  SERVICE_TABLE_ENTRYA *v10; // rax
  BYTE **v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // rcx
  BYTE *v14; // rcx
  DWORD v15; // r8d
  BYTE **v16; // rdx
  DWORD LastError; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  char Buffer[256]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v0 = (SERVICE_TABLE_ENTRYA *)&InetServiceDispatchTable;
  v1 = 0;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\InetInfo\\Parameters",
         0,
         0x20019u,
         &hKey) )
  {
    hKey = 0;
  }
  else
  {
    cbData = 0;
    if ( !RegQueryValueExA(hKey, "DispatchEntries", 0, &Type, 0, &cbData) )
    {
      v2 = 2;
      if ( cbData >= 2 )
      {
        v1 = (BYTE *)LocalAlloc(0, cbData);
        if ( v1 )
        {
          if ( RegQueryValueExA(hKey, "DispatchEntries", 0, &Type, v1, &cbData) )
            goto LABEL_22;
          if ( Type != 7 )
            goto LABEL_22;
          if ( cbData < 2 )
            goto LABEL_22;
          v3 = 0;
          v4 = v1;
          v5 = 0;
          v1[cbData - 1] = 0;
          v1[cbData - 2] = 0;
          v6 = cbData == 1;
          v7 = --cbData;
          if ( v6 )
            goto LABEL_22;
          do
          {
            v8 = *v4;
            v9 = v3 + 1;
            ++v4;
            if ( v8 )
              v9 = v3;
            ++v5;
            v3 = v9;
          }
          while ( v5 < v7 );
          if ( v9
            && (v10 = (SERVICE_TABLE_ENTRYA *)LocalAlloc(0, 16LL * (unsigned int)(v9 + 4)), (v11 = (BYTE **)v10) != 0) )
          {
            v0 = v10;
            v12 = 0;
            if ( InetServiceDispatchTable )
            {
              do
              {
                v13 = v12++;
                v13 *= 2;
                *v11 = (BYTE *)(&InetServiceDispatchTable)[v13];
                v11[1] = (BYTE *)(&InetServiceDispatchTable)[v13 + 1];
                v11 += 2;
              }
              while ( (&InetServiceDispatchTable)[2 * v12] );
            }
            *v11 = v1;
            v11[1] = (BYTE *)InetinfoStartService;
            v14 = v1;
            v15 = cbData;
            v16 = v11 + 2;
            if ( cbData > 2 )
            {
              do
              {
                if ( !*v14++ )
                {
                  *v16 = v14;
                  v16[1] = (BYTE *)InetinfoStartService;
                  v16 += 2;
                  v15 = cbData;
                }
                ++v2;
              }
              while ( v2 < v15 );
            }
            *v16 = 0;
            v16[1] = 0;
          }
          else
          {
LABEL_22:
            LocalFree(v1);
            v1 = 0;
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( !StartServiceCtrlDispatcherA(v0) )
  {
    LastError = GetLastError();
    sprintf_s(Buffer, 0x100u, "Inetinfo: Failed to start control dispatcher %lu\n", LastError);
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\iisrearc\\iisplus\\inetinfo\\main.cxx", 903, "StartDispatchTable", Buffer);
  }
  if ( v0 != (SERVICE_TABLE_ENTRYA *)&InetServiceDispatchTable )
  {
    LocalFree(v0);
    if ( v1 )
      LocalFree(v1);
  }
}

```

## disassembly

```asm
0x140002210  push    rbp
0x140002212  push    rbx
0x140002213  push    rsi
0x140002214  push    rdi
0x140002215  push    r14
0x140002217  push    r15
0x140002219  lea     rbp, [rsp-68h]
0x14000221e  sub     rsp, 168h
0x140002225  mov     rax, cs:__security_cookie
0x14000222c  xor     rax, rsp
0x14000222f  mov     [rbp+90h+var_40], rax
0x140002233  xor     r14d, r14d
0x140002236  lea     rax, [rsp+190h+hKey]
0x14000223b  lea     r15, ?InetServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYA@@A; _SERVICE_TABLE_ENTRYA near * InetServiceDispatchTable
0x140002242  mov     [rsp+190h+hKey], r14
0x140002247  mov     r9d, 20019h; samDesired
0x14000224d  mov     [rsp+190h+Type], r14d
0x140002252  xor     r8d, r8d; ulOptions
0x140002255  mov     [rsp+190h+cbData], r14d
0x14000225a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\In"...
0x140002261  mov     [rsp+190h+phkResult], rax; phkResult
0x140002266  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000226d  mov     rsi, r15
0x140002270  mov     ebx, r14d
0x140002273  call    cs:__imp_RegOpenKeyExA
0x140002279  test    eax, eax
0x14000227b  jz      short loc_140002287
0x14000227d  mov     [rsp+190h+hKey], r14
0x140002282  jmp     loc_14000242E
0x140002287  mov     rcx, [rsp+190h+hKey]; hKey
0x14000228c  lea     rax, [rsp+190h+cbData]
0x140002291  mov     [rsp+190h+lpcbData], rax; lpcbData
0x140002296  lea     r9, [rsp+190h+Type]; lpType
0x14000229b  xor     r8d, r8d; lpReserved
0x14000229e  mov     [rsp+190h+phkResult], r14; lpData
0x1400022a3  lea     rdx, aDispatchentrie; "DispatchEntries"
0x1400022aa  mov     [rsp+190h+cbData], r14d
0x1400022af  call    cs:__imp_RegQueryValueExA
0x1400022b5  test    eax, eax
0x1400022b7  jnz     loc_14000241E
0x1400022bd  lea     edi, [rax+2]
0x1400022c0  cmp     [rsp+190h+cbData], edi
0x1400022c4  jb      loc_14000241E
0x1400022ca  mov     edx, [rsp+190h+cbData]; uBytes
0x1400022ce  xor     ecx, ecx; uFlags
0x1400022d0  call    cs:__imp_LocalAlloc
0x1400022d6  mov     rbx, rax
0x1400022d9  test    rax, rax
0x1400022dc  jz      loc_14000241E
0x1400022e2  mov     rcx, [rsp+190h+hKey]; hKey
0x1400022e7  lea     rax, [rsp+190h+cbData]
0x1400022ec  mov     [rsp+190h+lpcbData], rax; lpcbData
0x1400022f1  lea     r9, [rsp+190h+Type]; lpType
0x1400022f6  xor     r8d, r8d; lpReserved
0x1400022f9  mov     [rsp+190h+phkResult], rbx; lpData
0x1400022fe  lea     rdx, aDispatchentrie; "DispatchEntries"
0x140002305  call    cs:__imp_RegQueryValueExA
0x14000230b  test    eax, eax
0x14000230d  jnz     loc_140002412
0x140002313  cmp     [rsp+190h+Type], 7
0x140002318  jnz     loc_140002412
0x14000231e  cmp     [rsp+190h+cbData], edi
0x140002322  jb      loc_140002412
0x140002328  mov     eax, [rsp+190h+cbData]
0x14000232c  mov     r8d, r14d
0x14000232f  mov     r9, rbx
0x140002332  mov     r10d, r14d
0x140002335  mov     [rax+rbx-1], r14b
0x14000233a  mov     eax, [rsp+190h+cbData]
0x14000233e  mov     [rax+rbx-2], r14b
0x140002343  mov     edx, [rsp+190h+cbData]
0x140002347  add     edx, 0FFFFFFFFh
0x14000234a  mov     [rsp+190h+cbData], edx
0x14000234e  jz      loc_140002412
0x140002354  mov     cl, [r9]
0x140002357  lea     eax, [r8+1]
0x14000235b  inc     r9
0x14000235e  test    cl, cl
0x140002360  cmovnz  eax, r8d
0x140002364  inc     r10d
0x140002367  mov     r8d, eax
0x14000236a  cmp     r10d, edx
0x14000236d  jb      short loc_140002354
0x14000236f  test    eax, eax
0x140002371  jz      loc_140002412
0x140002377  lea     edx, [rax+4]
0x14000237a  xor     ecx, ecx; uFlags
0x14000237c  shl     rdx, 4; uBytes
0x140002380  call    cs:__imp_LocalAlloc
0x140002386  mov     rdx, rax
0x140002389  test    rax, rax
0x14000238c  jz      loc_140002412
0x140002392  cmp     cs:?InetServiceDispatchTable@@3PAU_SERVICE_TABLE_ENTRYA@@A, r14; _SERVICE_TABLE_ENTRYA near * InetServiceDispatchTable
0x140002399  mov     rsi, rax
0x14000239c  mov     r8d, r14d
0x14000239f  jz      short loc_1400023CA
0x1400023a1  mov     ecx, r8d
0x1400023a4  inc     r8d
0x1400023a7  add     rcx, rcx
0x1400023aa  mov     rax, [r15+rcx*8]
0x1400023ae  mov     [rdx], rax
0x1400023b1  mov     rax, [r15+rcx*8+8]
0x1400023b6  mov     [rdx+8], rax
0x1400023ba  add     rdx, 10h
0x1400023be  mov     eax, r8d
0x1400023c1  add     rax, rax
0x1400023c4  cmp     [r15+rax*8], r14
0x1400023c8  jnz     short loc_1400023A1
0x1400023ca  mov     [rdx], rbx
0x1400023cd  lea     r9, ?InetinfoStartService@@YAXKQEAPEAD@Z; InetinfoStartService(ulong,char * * const)
0x1400023d4  mov     [rdx+8], r9
0x1400023d8  mov     rcx, rbx
0x1400023db  mov     r8d, [rsp+190h+cbData]
0x1400023e0  add     rdx, 10h
0x1400023e4  cmp     r8d, edi
0x1400023e7  jbe     short loc_140002409
0x1400023e9  mov     al, [rcx]
0x1400023eb  inc     rcx
0x1400023ee  test    al, al
0x1400023f0  jnz     short loc_140002402
0x1400023f2  mov     [rdx], rcx
0x1400023f5  mov     [rdx+8], r9
0x1400023f9  add     rdx, 10h
0x1400023fd  mov     r8d, [rsp+190h+cbData]
0x140002402  inc     edi
0x140002404  cmp     edi, r8d
0x140002407  jb      short loc_1400023E9
0x140002409  mov     [rdx], r14
0x14000240c  mov     [rdx+8], r14
0x140002410  jmp     short loc_14000241E
0x140002412  mov     rcx, rbx; hMem
0x140002415  call    cs:__imp_LocalFree
0x14000241b  mov     rbx, r14
0x14000241e  mov     rcx, [rsp+190h+hKey]; hKey
0x140002423  test    rcx, rcx
0x140002426  jz      short loc_14000242E
0x140002428  call    cs:__imp_RegCloseKey
0x14000242e  mov     rcx, rsi; lpServiceStartTable
0x140002431  call    cs:__imp_StartServiceCtrlDispatcherA
0x140002437  test    eax, eax
0x140002439  jnz     short loc_14000248F
0x14000243b  call    cs:__imp_GetLastError
0x140002441  lea     r8, aInetinfoFailed_2; "Inetinfo: Failed to start control dispa"...
0x140002448  mov     edx, 100h; BufferCount
0x14000244d  mov     r9d, eax
0x140002450  lea     rcx, [rsp+190h+Buffer]; Buffer
0x140002455  call    cs:__imp_sprintf_s
0x14000245b  test    cs:g_dwDebugFlags, 3
0x140002462  jz      short loc_14000248F
0x140002464  mov     rcx, cs:g_pDebug
0x14000246b  lea     rax, [rsp+190h+Buffer]
0x140002470  lea     r9, aStartdispatcht; "StartDispatchTable"
0x140002477  mov     [rsp+190h+phkResult], rax
0x14000247c  mov     r8d, 387h
0x140002482  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\iisplus\\inetin"...
0x140002489  call    cs:__imp_PuDbgPrint
0x14000248f  cmp     rsi, r15
0x140002492  jz      short loc_1400024AB
0x140002494  mov     rcx, rsi; hMem
0x140002497  call    cs:__imp_LocalFree
0x14000249d  test    rbx, rbx
0x1400024a0  jz      short loc_1400024AB
0x1400024a2  mov     rcx, rbx; hMem
0x1400024a5  call    cs:__imp_LocalFree
0x1400024ab  mov     rcx, [rbp+90h+var_40]
0x1400024af  xor     rcx, rsp; StackCookie
0x1400024b2  call    __security_check_cookie
0x1400024b7  add     rsp, 168h
0x1400024be  pop     r15
0x1400024c0  pop     r14
0x1400024c2  pop     rdi
0x1400024c3  pop     rsi
0x1400024c4  pop     rbx
0x1400024c5  pop     rbp
0x1400024c6  retn
```
