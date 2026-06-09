# RegUtils::GetRegDword(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x18000c12c`
- end: `0x18000c1b0`
- name: `?GetRegDword@RegUtils@@SAJPEBG0KPEAK@Z`
- size: `132`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000af38`
- `0x18000bef4`

## callees

- `0x18000c12c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c196`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c196`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c16e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c16e`

## pseudocode

```c
__int64 __fastcall RegUtils::GetRegDword(LPCWSTR lpSubKey, LPCWSTR lpValue, unsigned int a3, unsigned int *a4)
{
  int ValueW; // eax
  unsigned int v6; // ecx
  DWORD v8[6]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v8[0] = 4;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValue, 0x18u, 0, &v9, v8);
  if ( ValueW == 2 || !ValueW )
  {
    v6 = 0;
    *a4 = v9;
  }
  else
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    return (unsigned int)ZTraceReportOriginationNoThis(ValueW, "RegUtils::GetRegDword", 264);
  }
  return v6;
}

```

## disassembly

```asm
0x18000c12c  mov     r11, rsp
0x18000c12f  push    rbx
0x18000c130  sub     rsp, 50h
0x18000c134  lea     rax, [r11-18h]
0x18000c138  mov     [r11+18h], r8d
0x18000c13c  mov     [r11-28h], rax
0x18000c140  mov     r8, rdx; lpValue
0x18000c143  lea     rax, [r11+18h]
0x18000c147  mov     [rsp+58h+var_18], 4
0x18000c14f  mov     rbx, r9
0x18000c152  mov     [r11-30h], rax
0x18000c156  mov     rdx, rcx; lpSubKey
0x18000c159  mov     qword ptr [r11-38h], 0
0x18000c161  mov     r9d, 18h; dwFlags
0x18000c167  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c16e  call    cs:__imp_RegGetValueW
0x18000c174  cmp     eax, 2
0x18000c177  jz      short loc_18000C1A0
0x18000c179  test    eax, eax
0x18000c17b  jz      short loc_18000C1A0
0x18000c17d  jle     short loc_18000C187
0x18000c17f  movzx   eax, ax
0x18000c182  or      eax, 80070000h
0x18000c187  mov     r8d, 108h
0x18000c18d  lea     rdx, aRegutilsGetreg_0; "RegUtils::GetRegDword"
0x18000c194  mov     ecx, eax
0x18000c196  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c19c  mov     ecx, eax
0x18000c19e  jmp     short loc_18000C1A8
0x18000c1a0  mov     eax, [rsp+58h+arg_10]
0x18000c1a4  xor     ecx, ecx
0x18000c1a6  mov     [rbx], eax
0x18000c1a8  mov     eax, ecx
0x18000c1aa  add     rsp, 50h
0x18000c1ae  pop     rbx
0x18000c1af  retn
```
