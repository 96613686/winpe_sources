# fv::FilterValidation::FilterValidation(void)

- ea: `0x140056080`
- end: `0x1400561e3`
- name: `??0FilterValidation@fv@@QEAA@XZ`
- size: `355`
- prototype: `fv::FilterValidation *__fastcall(fv::FilterValidation *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140007fb0`

## callees

- `0x1400086f8`
- `0x140056080`
- `0x1400565a0`
- `0x14005715c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400561d1`
- `ADVAPI32!RegCloseKey` at `0x1400561d1`
- `ADVAPI32!RegOpenKeyExW` at `0x1400560bc`
- `ADVAPI32!RegOpenKeyExW` at `0x1400560bc`
- `ADVAPI32!RegQueryValueExW` at `0x1400560fb`
- `ADVAPI32!RegQueryValueExW` at `0x14005617c`
- `ADVAPI32!RegQueryValueExW` at `0x1400560fb`
- `ADVAPI32!RegQueryValueExW` at `0x14005617c`

## pseudocode

```c
fv::FilterValidation *__fastcall fv::FilterValidation::FilterValidation(fv::FilterValidation *this)
{
  DWORD v2; // ecx
  bool started; // al
  DWORD Data; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  *(_WORD *)this = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &hKey) )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"PipelineEnableVEH", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && Data == 1 )
    {
      *(_BYTE *)this = 1;
      RegisterSplVectoredHandler();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_89e2a8c1b7ed39c76597c34ba9e7630f_Traceguids);
    }
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(hKey, L"PipelineEnableTrackModules", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v2 = Data;
      if ( Data )
      {
        *((_BYTE *)this + 1) = 1;
        started = StartTracking(v2);
        *((_BYTE *)this + 1) = started;
        if ( started && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_89e2a8c1b7ed39c76597c34ba9e7630f_Traceguids);
      }
    }
    RegCloseKey(hKey);
  }
  return this;
}

```

## disassembly

```asm
0x140056080  push    rbp
0x140056082  push    rbx
0x140056083  push    r15
0x140056085  mov     rbp, rsp
0x140056088  sub     rsp, 30h
0x14005608c  mov     rbx, rcx
0x14005608f  mov     word ptr [rcx], 0
0x140056094  lea     rax, [rbp+hKey]
0x140056098  mov     [rbp+hKey], 0
0x1400560a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400560a7  mov     [rsp+30h+phkResult], rax; phkResult
0x1400560ac  mov     r9d, 20019h; samDesired
0x1400560b2  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Pri"...
0x1400560b9  xor     r8d, r8d; ulOptions
0x1400560bc  call    cs:__imp_RegOpenKeyExW
0x1400560c2  test    eax, eax
0x1400560c4  jnz     loc_1400561D7
0x1400560ca  mov     rcx, [rbp+hKey]; hKey
0x1400560ce  lea     r9, [rbp+Type]; lpType
0x1400560d2  mov     [rbp+Type], eax
0x1400560d5  lea     rdx, aPipelineenable; "PipelineEnableVEH"
0x1400560dc  mov     [rbp+Data], eax
0x1400560df  xor     r8d, r8d; lpReserved
0x1400560e2  lea     rax, [rbp+cbData]
0x1400560e6  mov     [rbp+cbData], 4
0x1400560ed  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1400560f2  lea     rax, [rbp+Data]
0x1400560f6  mov     [rsp+30h+phkResult], rax; lpData
0x1400560fb  call    cs:__imp_RegQueryValueExW
0x140056101  lea     r15, WPP_GLOBAL_Control
0x140056108  test    eax, eax
0x14005610a  jnz     short loc_14005614A
0x14005610c  cmp     [rbp+Type], 4
0x140056110  jnz     short loc_14005614A
0x140056112  cmp     [rbp+Data], 1
0x140056116  jnz     short loc_14005614A
0x140056118  mov     byte ptr [rbx], 1
0x14005611b  call    RegisterSplVectoredHandler
0x140056120  mov     rcx, cs:WPP_GLOBAL_Control
0x140056127  cmp     rcx, r15
0x14005612a  jz      short loc_14005614A
0x14005612c  test    dword ptr [rcx+1Ch], 100h
0x140056133  jz      short loc_14005614A
0x140056135  mov     rcx, [rcx+10h]
0x140056139  lea     r8, WPP_89e2a8c1b7ed39c76597c34ba9e7630f_Traceguids
0x140056140  mov     edx, 0Ah
0x140056145  call    WPP_SF_
0x14005614a  mov     rcx, [rbp+hKey]; hKey
0x14005614e  lea     rax, [rbp+cbData]
0x140056152  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140056157  lea     r9, [rbp+Type]; lpType
0x14005615b  lea     rax, [rbp+Data]
0x14005615f  mov     [rbp+cbData], 4
0x140056166  xor     r8d, r8d; lpReserved
0x140056169  mov     [rsp+30h+phkResult], rax; lpData
0x14005616e  lea     rdx, aPipelineenable_0; "PipelineEnableTrackModules"
0x140056175  mov     [rbp+Data], 0
0x14005617c  call    cs:__imp_RegQueryValueExW
0x140056182  test    eax, eax
0x140056184  jnz     short loc_1400561CD
0x140056186  cmp     [rbp+Type], 4
0x14005618a  jnz     short loc_1400561CD
0x14005618c  mov     ecx, [rbp+Data]; Period
0x14005618f  test    ecx, ecx
0x140056191  jz      short loc_1400561CD
0x140056193  mov     byte ptr [rbx+1], 1
0x140056197  call    ?StartTracking@@YA_NK@Z; StartTracking(ulong)
0x14005619c  mov     [rbx+1], al
0x14005619f  test    al, al
0x1400561a1  jz      short loc_1400561CD
0x1400561a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400561aa  cmp     rcx, r15
0x1400561ad  jz      short loc_1400561CD
0x1400561af  test    dword ptr [rcx+1Ch], 100h
0x1400561b6  jz      short loc_1400561CD
0x1400561b8  mov     rcx, [rcx+10h]
0x1400561bc  lea     r8, WPP_89e2a8c1b7ed39c76597c34ba9e7630f_Traceguids
0x1400561c3  mov     edx, 0Bh
0x1400561c8  call    WPP_SF_
0x1400561cd  mov     rcx, [rbp+hKey]; hKey
0x1400561d1  call    cs:__imp_RegCloseKey
0x1400561d7  mov     rax, rbx
0x1400561da  add     rsp, 30h
0x1400561de  pop     r15
0x1400561e0  pop     rbx
0x1400561e1  pop     rbp
0x1400561e2  retn
```
