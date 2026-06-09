# GetCurrentSessionString(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *,ushort *,ulong)

- ea: `0x140008504`
- end: `0x140008665`
- name: `?GetCurrentSessionString@@YAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0PEAGK@Z`
- size: `353`
- prototype: `int __high(const unsigned __int16 *, enum tagDMACCOUNTLOOKUPTYPE, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d860`

## callees

- `0x140008504`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400085be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400085be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008609`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008609`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000862e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000862e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000863d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000864d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000863d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000864d`
- `DMCmnUtils!BigStrcat` at `0x140008584`
- `DMCmnUtils!BigStrcat` at `0x140008584`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14000853b`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x14000853b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140008555`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140008555`

## pseudocode

```c
__int64 __fastcall GetCurrentSessionString(__int64 a1, __int64 a2, __int64 a3, void *a4, DWORD pdwType)
{
  WCHAR *v6; // rbx
  __int64 v7; // rcx
  signed int InternalAcctID; // edi
  HLOCAL v9; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v11; // rdx
  LSTATUS ValueW; // eax
  bool v13; // cc
  HKEY hkey; // [rsp+40h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-10h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+38h] BYREF
  int v18; // [rsp+94h] [rbp+3Ch]

  v18 = HIDWORD(a3);
  hkey = 0;
  pdwType = 0;
  hMem[0] = 0;
  v6 = 0;
  pcbData = 520;
  InternalAcctID = OmaDmGetInternalAcctID(a1, a2, hMem);
  if ( InternalAcctID >= 0 )
  {
    v9 = hMem[0];
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v7);
    v11 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    if ( !IsStateSeparationEnabled )
      v11 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
    v6 = BigStrcat(3u, v11, L"\\", v9);
    if ( v6 )
    {
      ValueW = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hkey);
      v13 = ValueW <= 0;
      if ( ValueW
        || (ValueW = RegGetValueW(hkey, 0, L"InitiationId", 2u, &pdwType, a4, &pcbData), v13 = ValueW <= 0, ValueW) )
      {
        if ( v13 )
          InternalAcctID = ValueW;
        else
          InternalAcctID = (unsigned __int16)ValueW | 0x80070000;
      }
      else if ( pdwType != 1 )
      {
        InternalAcctID = -2147418113;
      }
    }
    else
    {
      InternalAcctID = -2147024882;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  LocalFree(v6);
  LocalFree(hMem[0]);
  return (unsigned int)InternalAcctID;
}

```

## disassembly

```asm
0x140008504  mov     qword ptr [rsp-20h+arg_10], r8
0x140008509  push    rbp
0x14000850a  push    rbx
0x14000850b  push    rsi
0x14000850c  push    rdi
0x14000850d  mov     rbp, rsp
0x140008510  sub     rsp, 58h
0x140008514  lea     r8, [rbp+hMem]
0x140008518  mov     [rbp+hkey], 0
0x140008520  mov     rsi, r9
0x140008523  mov     [rbp+pdwType], 0
0x14000852a  mov     [rbp+hMem], 0
0x140008532  xor     ebx, ebx
0x140008534  mov     [rbp+arg_10], 208h
0x14000853b  call    cs:__imp_OmaDmGetInternalAcctID
0x140008542  nop     dword ptr [rax+rax+00h]
0x140008547  mov     edi, eax
0x140008549  test    eax, eax
0x14000854b  js      loc_140008625
0x140008551  mov     rbx, [rbp+hMem]
0x140008555  call    cs:__imp_RtlIsStateSeparationEnabled
0x14000855c  nop     dword ptr [rax+rax+00h]
0x140008561  lea     rcx, aSoftwareMicros_10; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140008568  mov     r9, rbx
0x14000856b  test    al, al
0x14000856d  lea     rdx, aOsdataSoftware_4; "OSData\\Software\\Microsoft\\Provisioni"...
0x140008574  lea     r8, pszSrc; "\\"
0x14000857b  cmovz   rdx, rcx
0x14000857f  mov     ecx, 3
0x140008584  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x14000858b  nop     dword ptr [rax+rax+00h]
0x140008590  mov     rbx, rax
0x140008593  test    rax, rax
0x140008596  jnz     short loc_1400085A2
0x140008598  mov     edi, 8007000Eh
0x14000859d  jmp     loc_140008625
0x1400085a2  lea     rax, [rbp+hkey]
0x1400085a6  mov     r9d, 20019h; samDesired
0x1400085ac  xor     r8d, r8d; ulOptions
0x1400085af  mov     [rsp+58h+phkResult], rax; phkResult
0x1400085b4  mov     rdx, rbx; lpSubKey
0x1400085b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400085be  call    cs:__imp_RegOpenKeyExW
0x1400085c5  nop     dword ptr [rax+rax+00h]
0x1400085ca  test    eax, eax
0x1400085cc  jz      short loc_1400085DF
0x1400085ce  jg      short loc_1400085D4
0x1400085d0  mov     edi, eax
0x1400085d2  jmp     short loc_140008625
0x1400085d4  movzx   edi, ax
0x1400085d7  or      edi, 80070000h
0x1400085dd  jmp     short loc_140008625
0x1400085df  mov     rcx, [rbp+hkey]; hkey
0x1400085e3  lea     rax, [rbp+arg_10]
0x1400085e7  mov     [rsp+58h+pcbData], rax; pcbData
0x1400085ec  lea     r8, Value; "InitiationId"
0x1400085f3  lea     rax, [rbp+pdwType]
0x1400085f7  mov     [rsp+58h+pvData], rsi; pvData
0x1400085fc  mov     r9d, 2; dwFlags
0x140008602  mov     [rsp+58h+phkResult], rax; pdwType
0x140008607  xor     edx, edx; lpSubKey
0x140008609  call    cs:__imp_RegGetValueW
0x140008610  nop     dword ptr [rax+rax+00h]
0x140008615  test    eax, eax
0x140008617  jnz     short loc_1400085CE
0x140008619  cmp     [rbp+pdwType], 1
0x14000861d  mov     eax, 8000FFFFh
0x140008622  cmovnz  edi, eax
0x140008625  mov     rcx, [rbp+hkey]; hKey
0x140008629  test    rcx, rcx
0x14000862c  jz      short loc_14000863A
0x14000862e  call    cs:__imp_RegCloseKey
0x140008635  nop     dword ptr [rax+rax+00h]
0x14000863a  mov     rcx, rbx; hMem
0x14000863d  call    cs:__imp_LocalFree
0x140008644  nop     dword ptr [rax+rax+00h]
0x140008649  mov     rcx, [rbp+hMem]; hMem
0x14000864d  call    cs:__imp_LocalFree
0x140008654  nop     dword ptr [rax+rax+00h]
0x140008659  mov     eax, edi
0x14000865b  add     rsp, 58h
0x14000865f  pop     rdi
0x140008660  pop     rsi
0x140008661  pop     rbx
0x140008662  pop     rbp
0x140008663  retn
```
