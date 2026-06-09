# NlSetDynamicSiteName_Old(ushort *)

- ea: `0x18004412c`
- end: `0x1800442d3`
- name: `?NlSetDynamicSiteName_Old@@YAXPEAG@Z`
- size: `423`
- prototype: `void __fastcall(BYTE *lpData)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180038944`
- `0x180038bb4`
- `0x18004370c`
- `0x180075b60`
- `0x180078454`
- `0x18007ea48`

## callees

- `0x180007518`
- `0x180024f38`
- `0x18004412c`
- `0x1800442dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044270`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044270`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044224`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180044224`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800442b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800441b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800441b0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800442a2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800442a2`
- `ntdll!RtlEnterCriticalSection` at `0x180044155`
- `ntdll!RtlEnterCriticalSection` at `0x180044155`

## string_xrefs

- `0x1800441c9`: `Cannot set site name to %ws from %ws since it is statically configured\n`
- `0x1800441ec`: `SYSTEM\CurrentControlSet\Services\Netlogon\Parameters`
- `0x180044207`: `Cannot NlOpenNetlogonKey to set site name to %ws from %ws\n`
- `0x180044237`: `NlSetDynamicSiteName: Cannot delete 'SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\%ws' %ld.\n`
- `0x180044280`: `NlSetDynamicSiteName: Cannot Set 'SYSTEM\CurrentControlSet\Services\Netlogon\Parameters\%ws' %ld.\n`

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
      if ( dword_1800F81F8 )
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
0x18004412c  mov     [rsp+arg_0], rbx
0x180044131  mov     [rsp+arg_8], rsi
0x180044136  push    rdi
0x180044137  sub     rsp, 30h
0x18004413b  xor     esi, esi
0x18004413d  mov     rbx, rcx
0x180044140  cmp     cs:?NlGlobalMemberWorkstation@@3HA, esi; int NlGlobalMemberWorkstation
0x180044146  jz      loc_1800442C2
0x18004414c  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180044153  mov     edi, esi
0x180044155  call    cs:__imp_RtlEnterCriticalSection
0x18004415c  nop     dword ptr [rax+rax+00h]
0x180044161  mov     r9, cs:?NlGlobalUnicodeSiteName@@3PEAGEA; ushort * NlGlobalUnicodeSiteName
0x180044168  test    r9, r9
0x18004416b  jz      short loc_1800441C1
0x18004416d  test    rbx, rbx
0x180044170  jz      short loc_1800441C1
0x180044172  mov     rcx, r9
0x180044175  mov     rax, rbx
0x180044178  sub     rcx, rbx
0x18004417b  movzx   edx, word ptr [rax]
0x18004417e  movzx   r8d, word ptr [rax+rcx]
0x180044183  sub     edx, r8d
0x180044186  jnz     short loc_180044191
0x180044188  add     rax, 2
0x18004418c  test    r8d, r8d
0x18004418f  jnz     short loc_18004417B
0x180044191  test    edx, edx
0x180044193  jnz     short loc_1800441C1
0x180044195  mov     r8, rbx
0x180044198  lea     rdx, aNlsetdynamicsi_1; "NlSetDynamicSiteName: Old and new site "...
0x18004419f  mov     ecx, 8000000h; unsigned int
0x1800441a4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800441a9  lea     rcx, ?NlGlobalSiteNameSetTime@@3T_LARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x1800441b0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800441b7  nop     dword ptr [rax+rax+00h]
0x1800441bc  jmp     loc_18004429B
0x1800441c1  cmp     cs:dword_1800F81F8, esi
0x1800441c7  jz      short loc_1800441E2
0x1800441c9  lea     rdx, aCannotSetSiteN; "Cannot set site name to %ws from %ws si"...
0x1800441d0  mov     ecx, 8000000h; unsigned int
0x1800441d5  mov     r8, rbx
0x1800441d8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800441dd  jmp     loc_18004429B
0x1800441e2  xor     edx, edx; unsigned __int8 *
0x1800441e4  mov     rcx, rbx; Src
0x1800441e7  call    ?NlSetSiteName_Old@@YAKPEAGPEAE@Z; NlSetSiteName_Old(ushort *,uchar *)
0x1800441ec  lea     rcx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800441f3  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x1800441f8  mov     rdi, rax
0x1800441fb  test    rax, rax
0x1800441fe  jnz     short loc_180044215
0x180044200  mov     r9, cs:?NlGlobalUnicodeSiteName@@3PEAGEA; ushort * NlGlobalUnicodeSiteName
0x180044207  lea     rdx, aCannotNlopenne; "Cannot NlOpenNetlogonKey to set site na"...
0x18004420e  mov     ecx, 100h
0x180044213  jmp     short loc_1800441D5
0x180044215  test    rbx, rbx
0x180044218  jnz     short loc_180044240
0x18004421a  lea     rdx, aDynamicsitenam; "DynamicSiteName"
0x180044221  mov     rcx, rdi; hKey
0x180044224  call    cs:__imp_RegDeleteValueW
0x18004422b  nop     dword ptr [rax+rax+00h]
0x180044230  test    eax, 0FFFFFFFDh
0x180044235  jz      short loc_18004429B
0x180044237  lea     rdx, aNlsetdynamicsi_0; "NlSetDynamicSiteName: Cannot delete 'SY"...
0x18004423e  jmp     short loc_180044287
0x180044240  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044244  inc     rax
0x180044247  cmp     [rbx+rax*2], si
0x18004424b  jnz     short loc_180044244
0x18004424d  lea     eax, ds:2[rax*2]
0x180044254  mov     r9d, 1; dwType
0x18004425a  mov     [rsp+38h+cbData], eax; cbData
0x18004425e  lea     rdx, aDynamicsitenam; "DynamicSiteName"
0x180044265  xor     r8d, r8d; Reserved
0x180044268  mov     [rsp+38h+lpData], rbx; lpData
0x18004426d  mov     rcx, rdi; hKey
0x180044270  call    cs:__imp_RegSetValueExW
0x180044277  nop     dword ptr [rax+rax+00h]
0x18004427c  test    eax, eax
0x18004427e  jz      short loc_18004429B
0x180044280  lea     rdx, aNlsetdynamicsi; "NlSetDynamicSiteName: Cannot Set 'SYSTE"...
0x180044287  mov     r9d, eax
0x18004428a  lea     r8, aDynamicsitenam; "DynamicSiteName"
0x180044291  mov     ecx, 100h; unsigned int
0x180044296  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18004429b  lea     rcx, ?NlGlobalSiteCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800442a2  call    cs:__imp_RtlLeaveCriticalSection
0x1800442a9  nop     dword ptr [rax+rax+00h]
0x1800442ae  test    rdi, rdi
0x1800442b1  jz      short loc_1800442C2
0x1800442b3  mov     rcx, rdi; hKey
0x1800442b6  call    cs:__imp_RegCloseKey
0x1800442bd  nop     dword ptr [rax+rax+00h]
0x1800442c2  mov     rbx, [rsp+38h+arg_0]
0x1800442c7  mov     rsi, [rsp+38h+arg_8]
0x1800442cc  add     rsp, 30h
0x1800442d0  pop     rdi
0x1800442d1  retn
```
