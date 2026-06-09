# OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(HKEY__ *,RtlNameValueArray const &)

- ea: `0x18000807c`
- end: `0x18000815b`
- name: `?WriteRegistryValues@OneSettingsQuery@Telemetry@Base@OneCore@@CAJPEAUHKEY__@@AEBVRtlNameValueArray@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(HKEY hKey, const struct RtlNameValueArray *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006eb0`
- `0x180007c90`

## callees

- `0x18000807c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000812a`
- `ADVAPI32!RegSetValueExW` at `0x18000812a`

## pseudocode

```c
LSTATUS __fastcall OneCore::Base::Telemetry::OneSettingsQuery::WriteRegistryValues(
        HKEY hKey,
        const struct RtlNameValueArray *a2)
{
  unsigned __int64 v4; // rbx
  const WCHAR **v5; // rax
  const WCHAR *v6; // r10
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  const BYTE *lpData; // rdx
  __int64 v11; // rax
  LSTATUS result; // eax

  if ( !*((_QWORD *)a2 + 2) )
    return 0;
  v4 = 0;
  while ( 1 )
  {
    if ( is_mul_ok(*((_QWORD *)a2 + 1), v4)
      && (v5 = (const WCHAR **)(*((_QWORD *)a2 + 5) + *((_QWORD *)a2 + 1) * v4),
          (unsigned __int64)v5 >= *((_QWORD *)a2 + 5)) )
    {
      v6 = *v5;
    }
    else
    {
      v6 = (const WCHAR *)MEMORY[0];
    }
    if ( !is_mul_ok(*((_QWORD *)a2 + 1), v4)
      || (v7 = (__int64 *)(*((_QWORD *)a2 + 5) + *((_QWORD *)a2 + 1) * v4), (unsigned __int64)v7 < *((_QWORD *)a2 + 5)) )
    {
      v7 = 0;
    }
    v8 = *v7;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    lpData = (const BYTE *)(v8 + 2 * (v9 + 1));
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&lpData[2 * v11] );
    result = RegSetValueExW(hKey, v6, 0, 1u, lpData, 2 * v11 + 2);
    if ( result )
      break;
    if ( ++v4 >= *((_QWORD *)a2 + 2) )
      return 0;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000807c  push    rbx
0x18000807e  push    rbp
0x18000807f  push    rsi
0x180008080  push    rdi
0x180008081  sub     rsp, 38h
0x180008085  mov     rax, [rdx+10h]
0x180008089  xor     ebp, ebp
0x18000808b  mov     rdi, rdx
0x18000808e  mov     rsi, rcx
0x180008091  test    rax, rax
0x180008094  jz      loc_180008144
0x18000809a  mov     ebx, ebp
0x18000809c  cmp     rbx, rax
0x18000809f  jnb     short loc_1800080DC
0x1800080a1  mov     rax, rbx
0x1800080a4  mul     qword ptr [rdi+8]
0x1800080a8  test    rdx, rdx
0x1800080ab  jnz     short loc_1800080BC
0x1800080ad  add     rax, [rdi+28h]
0x1800080b1  cmp     rax, [rdi+28h]
0x1800080b5  jb      short loc_1800080BC
0x1800080b7  mov     r10, [rax]
0x1800080ba  jmp     short loc_1800080C4
0x1800080bc  mov     r10, ds:0
0x1800080c4  mov     rax, rbx
0x1800080c7  mul     qword ptr [rdi+8]
0x1800080cb  test    rdx, rdx
0x1800080ce  jnz     short loc_1800080E4
0x1800080d0  add     rax, [rdi+28h]
0x1800080d4  cmp     rax, [rdi+28h]
0x1800080d8  jnb     short loc_1800080E7
0x1800080da  jmp     short loc_1800080E4
0x1800080dc  mov     r10, ds:0
0x1800080e4  mov     rax, rbp
0x1800080e7  mov     rcx, [rax]
0x1800080ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800080ee  inc     rax
0x1800080f1  cmp     [rcx+rax*2], bp
0x1800080f5  jnz     short loc_1800080EE
0x1800080f7  inc     rax
0x1800080fa  lea     rdx, [rcx+rax*2]
0x1800080fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008102  inc     rax
0x180008105  cmp     [rdx+rax*2], bp
0x180008109  jnz     short loc_180008102
0x18000810b  lea     eax, ds:2[rax*2]
0x180008112  mov     r9d, 1; dwType
0x180008118  mov     [rsp+58h+cbData], eax; cbData
0x18000811c  xor     r8d, r8d; Reserved
0x18000811f  mov     [rsp+58h+lpData], rdx; lpData
0x180008124  mov     rcx, rsi; hKey
0x180008127  mov     rdx, r10; lpValueName
0x18000812a  call    cs:__imp_RegSetValueExW
0x180008130  test    eax, eax
0x180008132  jnz     short loc_18000814F
0x180008134  mov     rax, [rdi+10h]
0x180008138  inc     rbx
0x18000813b  cmp     rbx, rax
0x18000813e  jb      loc_1800080A1
0x180008144  mov     eax, ebp
0x180008146  add     rsp, 38h
0x18000814a  pop     rdi
0x18000814b  pop     rsi
0x18000814c  pop     rbp
0x18000814d  pop     rbx
0x18000814e  retn
0x18000814f  jle     short loc_180008146
0x180008151  movzx   eax, ax
0x180008154  or      eax, 80070000h
0x180008159  jmp     short loc_180008146
```
