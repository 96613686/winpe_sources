# SxQueryDeviceRandomReadDiskScore(ulong,ulong *)

- ea: `0x1800391fc`
- end: `0x1800393ed`
- name: `?SxQueryDeviceRandomReadDiskScore@@YAJKPEAK@Z`
- size: `497`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001adac`
- `0x18003e618`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800193a0`
- `0x1800197a8`
- `0x18001bf30`
- `0x1800391fc`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039316`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039316`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800392e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800393b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800392e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800393b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003939e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003939e`

## string_xrefs

- `0x180039226`: `SxQueryDeviceRandomReadDiskScore`
- `0x18003934a`: `RandomReadDiskScore`

## pseudocode

```c
__int64 __fastcall SxQueryDeviceRandomReadDiskScore(int a1, unsigned int *a2)
{
  unsigned int v4; // edx
  void *v5; // rbx
  __int16 v6; // ax
  int DiskExts; // eax
  bool v8; // sf
  int v9; // eax
  __int16 v10; // ax
  unsigned int v11; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  int WinSatVolume; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v17; // [rsp+4Ch] [rbp-B4h]
  __int16 v18; // [rsp+4Eh] [rbp-B2h]
  WCHAR szVolumeName[264]; // [rsp+80h] [rbp-80h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&WinSatVolume, "SxQueryDeviceRandomReadDiskScore", 333, 1);
  memset_0(szVolumeName, 0, 0x20Au);
  v5 = 0;
  v6 = 342;
  pv = 0;
  hKey = 0;
  v14 = 0;
  if ( !a2 )
  {
    WinSatVolume = -2147024809;
    goto LABEL_17;
  }
  *a2 = 0;
  WinSatVolume = 0;
  v17 = 342;
  WinSatVolume = SxGetWinSatVolume(szVolumeName, v4);
  v6 = 348;
  if ( WinSatVolume < 0 )
    goto LABEL_17;
  v17 = 348;
  DiskExts = SxGetDiskExts(szVolumeName, (struct _VOLUME_DISK_EXTENTS **)&pv);
  v5 = pv;
  v8 = DiskExts < 0;
  WinSatVolume = DiskExts;
  v6 = 349;
  if ( v8 )
    goto LABEL_17;
  v17 = 349;
  if ( !*(_DWORD *)pv || *((_DWORD *)pv + 2) != a1 )
  {
    WinSatVolume = 1;
    v10 = 358;
    goto LABEL_14;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WinSat", 0, 0x20019u, &hKey);
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
  WinSatVolume = v9;
  v8 = v9 < 0;
  v6 = 365;
  if ( v8 )
    goto LABEL_17;
  v17 = 365;
  WinSatVolume = SxRegReadDWORD(hKey, L"RandomReadDiskScore", &v14, 1);
  if ( WinSatVolume >= 0 )
  {
    *a2 = v14;
    v10 = 374;
    WinSatVolume = 0;
LABEL_14:
    v17 = v10;
    goto LABEL_18;
  }
  v6 = 370;
LABEL_17:
  v18 = v6;
LABEL_18:
  CoTaskMemFree(v5);
  v11 = WinSatVolume;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&WinSatVolume);
  return v11;
}

```

## disassembly

```asm
0x1800391fc  push    rbp
0x1800391fe  push    rbx
0x1800391ff  push    rsi
0x180039200  push    rdi
0x180039201  lea     rbp, [rsp-1A8h]
0x180039209  sub     rsp, 2A8h
0x180039210  mov     rax, cs:__security_cookie
0x180039217  xor     rax, rsp
0x18003921a  mov     [rbp+1C0h+var_30], rax
0x180039221  mov     rdi, rdx
0x180039224  mov     esi, ecx
0x180039226  lea     rdx, aSxquerydevicer; "SxQueryDeviceRandomReadDiskScore"
0x18003922d  mov     r9d, 1; unsigned __int16
0x180039233  lea     rcx, [rsp+2C0h+var_278]; this
0x180039238  mov     r8d, 14Dh; unsigned __int16
0x18003923e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180039243  xor     edx, edx; Val
0x180039245  lea     rcx, [rbp+1C0h+szVolumeName]; void *
0x180039249  mov     r8d, 20Ah; Size
0x18003924f  call    memset_0
0x180039254  xor     ebx, ebx
0x180039256  mov     eax, 156h
0x18003925b  mov     [rsp+2C0h+pv], rbx
0x180039260  mov     [rsp+2C0h+hKey], rbx
0x180039265  mov     [rsp+2C0h+var_288], ebx
0x180039269  test    rdi, rdi
0x18003926c  jz      loc_18003938E
0x180039272  lea     rcx, [rbp+1C0h+szVolumeName]; lpszVolumeName
0x180039276  mov     [rdi], ebx
0x180039278  mov     [rsp+2C0h+var_278], ebx
0x18003927c  mov     [rsp+2C0h+var_274], ax
0x180039281  call    ?SxGetWinSatVolume@@YAJPEAGK@Z; SxGetWinSatVolume(ushort *,ulong)
0x180039286  mov     [rsp+2C0h+var_278], eax
0x18003928a  test    eax, eax
0x18003928c  mov     eax, 15Ch
0x180039291  js      loc_180039396
0x180039297  lea     rdx, [rsp+2C0h+pv]; struct _VOLUME_DISK_EXTENTS **
0x18003929c  mov     [rsp+2C0h+var_274], ax
0x1800392a1  lea     rcx, [rbp+1C0h+szVolumeName]; unsigned __int16 *
0x1800392a5  call    ?SxGetDiskExts@@YAJPEBGPEAPEAU_VOLUME_DISK_EXTENTS@@@Z; SxGetDiskExts(ushort const *,_VOLUME_DISK_EXTENTS * *)
0x1800392aa  mov     rbx, [rsp+2C0h+pv]
0x1800392af  test    eax, eax
0x1800392b1  mov     [rsp+2C0h+var_278], eax
0x1800392b5  mov     eax, 15Dh
0x1800392ba  js      loc_180039396
0x1800392c0  mov     [rsp+2C0h+var_274], ax
0x1800392c5  cmp     dword ptr [rbx], 0
0x1800392c8  jz      loc_18003937F
0x1800392ce  cmp     [rbx+8], esi
0x1800392d1  jnz     loc_18003937F
0x1800392d7  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800392dc  lea     rax, [rcx-1]
0x1800392e0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800392e4  ja      short loc_1800392F5
0x1800392e6  call    cs:__imp_RegCloseKey
0x1800392ec  mov     [rsp+2C0h+hKey], 0
0x1800392f5  lea     rax, [rsp+2C0h+hKey]
0x1800392fa  mov     r9d, 20019h; samDesired
0x180039300  xor     r8d, r8d; ulOptions
0x180039303  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180039308  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003930f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180039316  call    cs:__imp_RegOpenKeyExW
0x18003931c  test    eax, eax
0x18003931e  jle     short loc_180039328
0x180039320  movzx   eax, ax
0x180039323  or      eax, 80070000h
0x180039328  mov     [rsp+2C0h+var_278], eax
0x18003932c  test    eax, eax
0x18003932e  mov     eax, 16Dh
0x180039333  js      short loc_180039396
0x180039335  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003933a  lea     r8, [rsp+2C0h+var_288]; unsigned int *
0x18003933f  mov     r9d, 1; int
0x180039345  mov     [rsp+2C0h+var_274], ax
0x18003934a  lea     rdx, aRandomreaddisk; "RandomReadDiskScore"
0x180039351  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180039356  mov     [rsp+2C0h+var_278], eax
0x18003935a  test    eax, eax
0x18003935c  jns     short loc_180039365
0x18003935e  mov     eax, 172h
0x180039363  jmp     short loc_180039396
0x180039365  mov     eax, [rsp+2C0h+var_288]
0x180039369  mov     [rdi], eax
0x18003936b  mov     eax, 176h
0x180039370  mov     [rsp+2C0h+var_278], 0
0x180039378  mov     [rsp+2C0h+var_274], ax
0x18003937d  jmp     short loc_18003939B
0x18003937f  mov     [rsp+2C0h+var_278], 1
0x180039387  mov     eax, 166h
0x18003938c  jmp     short loc_180039378
0x18003938e  mov     [rsp+2C0h+var_278], 80070057h
0x180039396  mov     [rsp+2C0h+var_272], ax
0x18003939b  mov     rcx, rbx; pv
0x18003939e  call    cs:__imp_CoTaskMemFree
0x1800393a4  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800393a9  mov     ebx, [rsp+2C0h+var_278]
0x1800393ad  lea     rdx, [rcx-1]
0x1800393b1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800393b5  ja      short loc_1800393C6
0x1800393b7  call    cs:__imp_RegCloseKey
0x1800393bd  mov     [rsp+2C0h+hKey], 0
0x1800393c6  lea     rcx, [rsp+2C0h+var_278]; this
0x1800393cb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800393d0  mov     eax, ebx
0x1800393d2  mov     rcx, [rbp+1C0h+var_30]
0x1800393d9  xor     rcx, rsp; StackCookie
0x1800393dc  call    __security_check_cookie
0x1800393e1  add     rsp, 2A8h
0x1800393e8  pop     rdi
0x1800393e9  pop     rsi
0x1800393ea  pop     rbx
0x1800393eb  pop     rbp
0x1800393ec  retn
```
