# RegUtils::GetRegBoolean(ushort const *,ushort const *,bool,bool *)

- ea: `0x18000c088`
- end: `0x18000c123`
- name: `?GetRegBoolean@RegUtils@@SAJPEBG0_NPEA_N@Z`
- size: `155`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, __int64, bool *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000a6a4`

## callees

- `0x18000c088`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c103`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c103`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c0d6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000c0d6`

## string_xrefs

- `0x18000c0b2`: `InstallUpdateStarted`

## pseudocode

```c
__int64 __fastcall RegUtils::GetRegBoolean(LPCWSTR lpSubKey, const unsigned __int16 *a2, __int64 a3, bool *a4)
{
  unsigned int v4; // edi
  int ValueW; // eax
  DWORD v8; // [rsp+58h] [rbp+10h] BYREF
  int v9; // [rsp+5Ch] [rbp+14h]
  int v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = HIDWORD(a2);
  v4 = 0;
  v8 = 4;
  v10 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, lpSubKey, L"InstallUpdateStarted", 0x18u, 0, &v10, &v8);
  if ( ValueW == 2 )
  {
    *a4 = 0;
  }
  else if ( ValueW )
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    return (unsigned int)ZTraceReportOriginationNoThis(ValueW, "RegUtils::GetRegBoolean", 188);
  }
  else
  {
    *a4 = v10 != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000c088  mov     r11, rsp
0x18000c08b  mov     [r11+8], rbx
0x18000c08f  mov     [r11+18h], r8b
0x18000c093  mov     [r11+10h], rdx
0x18000c097  push    rdi
0x18000c098  sub     rsp, 40h
0x18000c09c  xor     edi, edi
0x18000c09e  mov     [rsp+48h+arg_8], 4
0x18000c0a6  lea     rax, [r11+10h]
0x18000c0aa  mov     [rsp+48h+arg_10], edi
0x18000c0ae  mov     [r11-18h], rax
0x18000c0b2  lea     r8, Value; "InstallUpdateStarted"
0x18000c0b9  lea     rax, [r11+18h]
0x18000c0bd  mov     rbx, r9
0x18000c0c0  mov     rdx, rcx; lpSubKey
0x18000c0c3  mov     [r11-20h], rax
0x18000c0c7  lea     r9d, [rdi+18h]; dwFlags
0x18000c0cb  mov     [r11-28h], rdi
0x18000c0cf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000c0d6  call    cs:__imp_RegGetValueW
0x18000c0dc  cmp     eax, 2
0x18000c0df  jnz     short loc_18000C0E6
0x18000c0e1  mov     [rbx], dil
0x18000c0e4  jmp     short loc_18000C116
0x18000c0e6  test    eax, eax
0x18000c0e8  jz      short loc_18000C10D
0x18000c0ea  jle     short loc_18000C0F4
0x18000c0ec  movzx   eax, ax
0x18000c0ef  or      eax, 80070000h
0x18000c0f4  mov     r8d, 0BCh
0x18000c0fa  lea     rdx, aRegutilsGetreg_1; "RegUtils::GetRegBoolean"
0x18000c101  mov     ecx, eax
0x18000c103  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c109  mov     edi, eax
0x18000c10b  jmp     short loc_18000C116
0x18000c10d  cmp     [rsp+48h+arg_10], edi
0x18000c111  setnz   al
0x18000c114  mov     [rbx], al
0x18000c116  mov     rbx, [rsp+48h+arg_0]
0x18000c11b  mov     eax, edi
0x18000c11d  add     rsp, 40h
0x18000c121  pop     rdi
0x18000c122  retn
```
