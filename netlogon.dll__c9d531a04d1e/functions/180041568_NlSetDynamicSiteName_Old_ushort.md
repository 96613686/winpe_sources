# NlSetDynamicSiteName_Old(ushort *)

- ea: `0x180041568`
- end: `0x1800416ea`
- name: `?NlSetDynamicSiteName_Old@@YAXPEAG@Z`
- size: `386`
- prototype: `void __fastcall(BYTE *lpData)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003682c`
- `0x180036a84`
- `0x180040bf8`
- `0x18007070c`
- `0x180072dc4`
- `0x180078f00`

## callees

- `0x180007278`
- `0x180023eb0`
- `0x180041568`
- `0x1800416f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004169a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004169a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180041654`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180041654`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800416d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800416d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800415e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800415e6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800416c6`
- `ntdll!RtlLeaveCriticalSection` at `0x1800416c6`
- `ntdll!RtlEnterCriticalSection` at `0x180041591`
- `ntdll!RtlEnterCriticalSection` at `0x180041591`

## string_xrefs

- `0x1800415f9`: `Cannot set site name to %ws from %ws since it is statically configured\n`
- `0x18004161c`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`
- `0x180041637`: `Cannot NlOpenNetlogonKey to set site name to %ws from %ws\n`
- `0x180041661`: `NlSetDynamicSiteName: Cannot delete 'SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\%ws' %ld.\n`
- `0x1800416a4`: `NlSetDynamicSiteName: Cannot Set 'SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\%ws' %ld.\n`

## pseudocode

```c
void __fastcall NlSetDynamicSiteName_Old(BYTE *lpData)
{
  HKEY v2; // rdi
  BYTE *v3; // rax
  int v4; // r8d
  int v5; // edx
  HKEY v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rax
  unsigned int v9; // eax

  if ( NlGlobalMemberWorkstation )
  {
    v2 = 0;
    RtlEnterCriticalSection(&NlGlobalSiteCritSect);
    if ( !NlGlobalUnicodeSiteName || !lpData )
      goto LABEL_9;
    v3 = lpData;
    do
    {
      v4 = *(unsigned __int16 *)&v3[(_BYTE *)NlGlobalUnicodeSiteName - lpData];
      v5 = *(unsigned __int16 *)v3 - v4;
      if ( v5 )
        break;
      v3 += 2;
    }
    while ( v4 );
    if ( !v5 )
    {
      NlPrintRoutine(0x8000000u, L"NlSetDynamicSiteName: Old and new site names '%ws' are identical.\n", lpData);
      GetSystemTimeAsFileTime(&NlGlobalSiteNameSetTime);
    }
    else
    {
LABEL_9:
      if ( dword_1800F11F8 )
      {
        NlPrintRoutine(0x8000000u, L"Cannot set site name to %ws from %ws since it is statically configured\n", lpData);
      }
      else
      {
        NlSetSiteName_Old((unsigned __int16 *)lpData, 0);
        v6 = NlOpenNetlogonKey("SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters");
        v2 = v6;
        if ( v6 )
        {
          if ( lpData )
          {
            v8 = -1;
            do
              ++v8;
            while ( *(_WORD *)&lpData[2 * v8] );
            v9 = RegSetValueExW(v2, L"DynamicSiteName", 0, 1u, lpData, 2 * v8 + 2);
            if ( v9 )
              NlPrintRoutine(
                0x100u,
                L"NlSetDynamicSiteName: Cannot Set 'SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters\\%ws' %ld.\n",
                L"DynamicSiteName",
                v9);
          }
          else
          {
            v7 = RegDeleteValueW(v6, L"DynamicSiteName");
            if ( (v7 & 0xFFFFFFFD) != 0 )
              NlPrintRoutine(
                0x100u,
                L"NlSetDynamicSiteName: Cannot delete 'SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Parameters\\%ws' %ld.\n",
                L"DynamicSiteName",
                v7);
          }
        }
        else
        {
          NlPrintRoutine(0x100u, L"Cannot NlOpenNetlogonKey to set site name to %ws from %ws\n", lpData);
        }
      }
    }
    RtlLeaveCriticalSection(&NlGlobalSiteCritSect);
    if ( v2 )
      RegCloseKey(v2);
  }
}

```

## disassembly

```asm
0x180041568  mov     [rsp+arg_0], rbx
0x18004156d  mov     [rsp+arg_8], rsi
0x180041572  push    rdi
0x180041573  sub     rsp, 30h
0x180041577  xor     esi, esi
0x180041579  mov     rbx, rcx
0x18004157c  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180041582  jz      loc_1800416DA
0x180041588  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18004158f  mov     edi, esi
0x180041591  call    cs:__imp_RtlEnterCriticalSection
0x180041597  mov     r9, cs:?NlGlobalUnicodeSiteName@@3PEAGEA; ushort * NlGlobalUnicodeSiteName
0x18004159e  test    r9, r9
0x1800415a1  jz      short loc_1800415F1
0x1800415a3  test    rbx, rbx
0x1800415a6  jz      short loc_1800415F1
0x1800415a8  mov     rcx, r9
0x1800415ab  mov     rax, rbx
0x1800415ae  sub     rcx, rbx
0x1800415b1  movzx   edx, word ptr [rax]
0x1800415b4  movzx   r8d, word ptr [rax+rcx]
0x1800415b9  sub     edx, r8d
0x1800415bc  jnz     short loc_1800415C7
0x1800415be  add     rax, 2
0x1800415c2  test    r8d, r8d
0x1800415c5  jnz     short loc_1800415B1
0x1800415c7  test    edx, edx
0x1800415c9  jnz     short loc_1800415F1
0x1800415cb  mov     r8, rbx
0x1800415ce  lea     rdx, aNlsetdynamicsi_1; "NlSetDynamicSiteName: Old and new site "...
0x1800415d5  mov     ecx, 8000000h; unsigned int
0x1800415da  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800415df  lea     rcx, ?NlGlobalSiteNameSetTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x1800415e6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800415ec  jmp     loc_1800416BF
0x1800415f1  cmp     cs:dword_1800F11F8, esi
0x1800415f7  jz      short loc_180041612
0x1800415f9  lea     rdx, aCannotSetSiteN; "Cannot set site name to %ws from %ws si"...
0x180041600  mov     ecx, 8000000h; unsigned int
0x180041605  mov     r8, rbx
0x180041608  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004160d  jmp     loc_1800416BF
0x180041612  xor     edx, edx; unsigned __int8 *
0x180041614  mov     rcx, rbx; Src
0x180041617  call    ?NlSetSiteName_Old@@YAKPEAGPEAE@Z; NlSetSiteName_Old(ushort *,uchar *)
0x18004161c  lea     rcx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180041623  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180041628  mov     rdi, rax
0x18004162b  test    rax, rax
0x18004162e  jnz     short loc_180041645
0x180041630  mov     r9, cs:?NlGlobalUnicodeSiteName@@3PEAGEA; ushort * NlGlobalUnicodeSiteName
0x180041637  lea     rdx, aCannotNlopenne; "Cannot NlOpenNetlogonKey to set site na"...
0x18004163e  mov     ecx, 100h
0x180041643  jmp     short loc_180041605
0x180041645  test    rbx, rbx
0x180041648  jnz     short loc_18004166A
0x18004164a  lea     rdx, aDynamicsitenam; "DynamicSiteName"
0x180041651  mov     rcx, rdi; hKey
0x180041654  call    cs:__imp_RegDeleteValueW
0x18004165a  test    eax, 0FFFFFFFDh
0x18004165f  jz      short loc_1800416BF
0x180041661  lea     rdx, aNlsetdynamicsi_0; "NlSetDynamicSiteName: Cannot delete 'SY"...
0x180041668  jmp     short loc_1800416AB
0x18004166a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004166e  inc     rax
0x180041671  cmp     [rbx+rax*2], si
0x180041675  jnz     short loc_18004166E
0x180041677  lea     eax, ds:2[rax*2]
0x18004167e  mov     r9d, 1; dwType
0x180041684  mov     [rsp+38h+cbData], eax; cbData
0x180041688  lea     rdx, aDynamicsitenam; "DynamicSiteName"
0x18004168f  xor     r8d, r8d; Reserved
0x180041692  mov     [rsp+38h+lpData], rbx; lpData
0x180041697  mov     rcx, rdi; hKey
0x18004169a  call    cs:__imp_RegSetValueExW
0x1800416a0  test    eax, eax
0x1800416a2  jz      short loc_1800416BF
0x1800416a4  lea     rdx, aNlsetdynamicsi; "NlSetDynamicSiteName: Cannot Set 'SYSTE"...
0x1800416ab  mov     r9d, eax
0x1800416ae  lea     r8, aDynamicsitenam; "DynamicSiteName"
0x1800416b5  mov     ecx, 100h; unsigned int
0x1800416ba  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800416bf  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800416c6  call    cs:__imp_RtlLeaveCriticalSection
0x1800416cc  test    rdi, rdi
0x1800416cf  jz      short loc_1800416DA
0x1800416d1  mov     rcx, rdi; hKey
0x1800416d4  call    cs:__imp_RegCloseKey
0x1800416da  mov     rbx, [rsp+38h+arg_0]
0x1800416df  mov     rsi, [rsp+38h+arg_8]
0x1800416e4  add     rsp, 30h
0x1800416e8  pop     rdi
0x1800416e9  retn
```
