# RegUtils::GetRegDword(ushort const *,ushort const *,ulong,ulong *)

- ea: `0x180007c04`
- end: `0x180007c98`
- name: `?GetRegDword@RegUtils@@SAJPEBG0KPEAK@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800072f0`

## callees

- `0x180007c04`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c7e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c7e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007c56`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180007c56`

## string_xrefs

- `0x180007c24`: `MapsTaskDisabled`

## pseudocode

```c
__int64 __fastcall RegUtils::GetRegDword(LPCWSTR lpSubKey, const unsigned __int16 *a2, __int64 a3, unsigned int *a4)
{
  int ValueW; // eax
  unsigned int v6; // ecx
  DWORD v8; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+5Ch] [rbp+14h]
  unsigned int v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = HIDWORD(a2);
  v8 = 4;
  v10 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"MapsTaskDisabled", 0x18u, 0, &v10, &v8);
  if ( ValueW == 2 || !ValueW )
  {
    v6 = 0;
    *a4 = v10;
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
0x180007c04  mov     r11, rsp
0x180007c07  mov     [r11+18h], r8d
0x180007c0b  mov     [r11+10h], rdx
0x180007c0f  push    rbx
0x180007c10  sub     rsp, 40h
0x180007c14  lea     rax, [r11+10h]
0x180007c18  mov     [rsp+48h+arg_8], 4
0x180007c20  mov     [r11-18h], rax
0x180007c24  lea     r8, Value; "MapsTaskDisabled"
0x180007c2b  lea     rax, [r11+18h]
0x180007c2f  mov     [rsp+48h+arg_10], 0
0x180007c37  mov     rbx, r9
0x180007c3a  mov     [r11-20h], rax
0x180007c3e  mov     rdx, rcx; lpSubKey
0x180007c41  mov     qword ptr [r11-28h], 0
0x180007c49  mov     r9d, 18h; dwFlags
0x180007c4f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180007c56  call    cs:__imp_RegGetValueW
0x180007c5c  cmp     eax, 2
0x180007c5f  jz      short loc_180007C88
0x180007c61  test    eax, eax
0x180007c63  jz      short loc_180007C88
0x180007c65  jle     short loc_180007C6F
0x180007c67  movzx   eax, ax
0x180007c6a  or      eax, 80070000h
0x180007c6f  mov     r8d, 108h
0x180007c75  lea     rdx, aRegutilsGetreg; "RegUtils::GetRegDword"
0x180007c7c  mov     ecx, eax
0x180007c7e  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007c84  mov     ecx, eax
0x180007c86  jmp     short loc_180007C90
0x180007c88  mov     eax, [rsp+48h+arg_10]
0x180007c8c  xor     ecx, ecx
0x180007c8e  mov     [rbx], eax
0x180007c90  mov     eax, ecx
0x180007c92  add     rsp, 40h
0x180007c96  pop     rbx
0x180007c97  retn
```
