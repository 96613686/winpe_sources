# DwMarkInterfaceKeyAsVPN(ushort *,ushort *,ulong)

- ea: `0x18006b180`
- end: `0x18006b37e`
- name: `?DwMarkInterfaceKeyAsVPN@@YAKPEAG0K@Z`
- size: `510`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800699c4`

## callees

- `0x180025e2c`
- `0x18006b180`
- `0x18006b82c`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18006b2e0`
- `ADVAPI32!RegSetValueExW` at `0x18006b2e0`
- `ADVAPI32!RegOpenKeyExW` at `0x18006b2b2`
- `ADVAPI32!RegOpenKeyExW` at `0x18006b2b2`
- `ADVAPI32!RegCloseKey` at `0x18006b325`
- `ADVAPI32!RegCloseKey` at `0x18006b325`

## string_xrefs

- `0x18006b20a`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x18006b228`: `DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error`
- `0x18006b32d`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`
- `0x18006b347`: `DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key`

## pseudocode

```c
__int64 __fastcall DwMarkInterfaceKeyAsVPN(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  WCHAR *v5; // r9
  __int64 v7; // rax
  unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  BYTE Data[8]; // [rsp+30h] [rbp-248h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-240h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF

  *(_DWORD *)Data = 1;
  hKey = 0;
  v5 = SubKey;
  v7 = 2147483646;
  v8 = a2;
  v9 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v5++ = *v8++;
    --v7;
    --v9;
  }
  while ( v9 );
  v10 = v5 - 1;
  v11 = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v5;
  *v10 = 0;
  if ( v9 )
  {
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( a1[v15] );
    do
      ++v14;
    while ( a2[v14] );
    v11 = StringCchCatW(SubKey, v15 + v14 + 1, a1);
    if ( v11 )
    {
      TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error");
      v12 = xmmword_1800CA020;
      if ( (_QWORD)xmmword_1800CA020 )
      {
        v13 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCatW returned error";
        goto LABEL_23;
      }
    }
    else
    {
      v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
      if ( v11 )
      {
        TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key");
        v12 = xmmword_1800CA020;
        if ( (_QWORD)xmmword_1800CA020 )
        {
          v13 = L"DwMarkInterfaceKeyAsVPN : Failed to Open the Registry Key";
          goto LABEL_23;
        }
      }
      else
      {
        v11 = RegSetValueExW(hKey, L"VPNInterface", 0, 4u, Data, 4u);
        if ( v11 )
        {
          TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
          if ( (_QWORD)xmmword_1800CA020 )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRegHelpTemplateFunc)(
              gRegHelpEtwContext,
              xmmword_1800CA020,
              L"DwMarkInterfaceKeyAsVPN : Failed to set the flag VPNInterface to 1");
        }
        RegCloseKey(hKey);
      }
    }
  }
  else
  {
    TraceIt(a3, "DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error");
    v12 = xmmword_1800CA020;
    if ( (_QWORD)xmmword_1800CA020 )
    {
      v13 = L"DwMarkInterfaceKeyAsVPN : Call to StringCchCopyW returned error";
LABEL_23:
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRegHelpTemplateFunc)(gRegHelpEtwContext, v12, v13);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18006b180  push    rbx
0x18006b182  push    rsi
0x18006b183  push    rdi
0x18006b184  sub     rsp, 260h
0x18006b18b  mov     rax, cs:__security_cookie
0x18006b192  xor     rax, rsp
0x18006b195  mov     [rsp+278h+var_28], rax
0x18006b19d  xor     esi, esi
0x18006b19f  mov     dword ptr [rsp+278h+Data], 1
0x18006b1a7  mov     edi, r8d
0x18006b1aa  mov     [rsp+278h+hKey], rsi
0x18006b1af  mov     r10, rcx
0x18006b1b2  lea     r9, [rsp+278h+SubKey]
0x18006b1b7  mov     r11, rdx
0x18006b1ba  mov     eax, 7FFFFFFEh
0x18006b1bf  mov     rcx, rdx
0x18006b1c2  mov     r8d, 104h
0x18006b1c8  test    rax, rax
0x18006b1cb  jz      short loc_18006B1EA
0x18006b1cd  movzx   edx, word ptr [rcx]
0x18006b1d0  test    dx, dx
0x18006b1d3  jz      short loc_18006B1EA
0x18006b1d5  mov     [r9], dx
0x18006b1d9  add     rcx, 2
0x18006b1dd  add     r9, 2
0x18006b1e1  dec     rax
0x18006b1e4  sub     r8, 1
0x18006b1e8  jnz     short loc_18006B1C8
0x18006b1ea  mov     rax, r8
0x18006b1ed  lea     rdx, [r9-2]
0x18006b1f1  neg     rax
0x18006b1f4  sbb     ebx, ebx
0x18006b1f6  not     ebx
0x18006b1f8  and     ebx, 8007007Ah
0x18006b1fe  test    r8, r8
0x18006b201  cmovnz  rdx, r9
0x18006b205  mov     [rdx], si
0x18006b208  jnz     short loc_18006B234
0x18006b20a  lea     rdx, aDwmarkinterfac_5; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006b211  mov     ecx, edi; unsigned int
0x18006b213  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006b218  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006b21f  test    rdx, rdx
0x18006b222  jz      loc_18006B361
0x18006b228  lea     r8, aDwmarkinterfac_7; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006b22f  jmp     loc_18006B34E
0x18006b234  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006b238  mov     rcx, rax
0x18006b23b  inc     rcx
0x18006b23e  cmp     [r10+rcx*2], si
0x18006b243  jnz     short loc_18006B23B
0x18006b245  inc     rax
0x18006b248  cmp     [r11+rax*2], si
0x18006b24d  jnz     short loc_18006B245
0x18006b24f  lea     rdx, [rax+1]
0x18006b253  mov     r8, r10; unsigned __int16 *
0x18006b256  add     rdx, rcx; unsigned __int64
0x18006b259  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18006b25e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006b263  mov     ebx, eax
0x18006b265  test    eax, eax
0x18006b267  jz      short loc_18006B293
0x18006b269  lea     rdx, aDwmarkinterfac_1; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006b270  mov     ecx, edi; unsigned int
0x18006b272  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006b277  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006b27e  test    rdx, rdx
0x18006b281  jz      loc_18006B361
0x18006b287  lea     r8, aDwmarkinterfac; "DwMarkInterfaceKeyAsVPN : Call to Strin"...
0x18006b28e  jmp     loc_18006B34E
0x18006b293  lea     rax, [rsp+278h+hKey]
0x18006b298  mov     r9d, 20006h; samDesired
0x18006b29e  xor     r8d, r8d; ulOptions
0x18006b2a1  mov     [rsp+278h+phkResult], rax; phkResult
0x18006b2a6  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18006b2ab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006b2b2  call    cs:__imp_RegOpenKeyExW
0x18006b2b8  mov     ebx, eax
0x18006b2ba  test    eax, eax
0x18006b2bc  jnz     short loc_18006B32D
0x18006b2be  mov     rcx, [rsp+278h+hKey]; hKey
0x18006b2c3  lea     r9d, [rax+4]; dwType
0x18006b2c7  lea     rax, [rsp+278h+Data]
0x18006b2cc  mov     [rsp+278h+cbData], r9d; cbData
0x18006b2d1  xor     r8d, r8d; Reserved
0x18006b2d4  mov     [rsp+278h+phkResult], rax; lpData
0x18006b2d9  lea     rdx, aVpninterface; "VPNInterface"
0x18006b2e0  call    cs:__imp_RegSetValueExW
0x18006b2e6  mov     ebx, eax
0x18006b2e8  test    eax, eax
0x18006b2ea  jz      short loc_18006B320
0x18006b2ec  lea     rdx, aDwmarkinterfac_8; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x18006b2f3  mov     ecx, edi; unsigned int
0x18006b2f5  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006b2fa  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006b301  test    rdx, rdx
0x18006b304  jz      short loc_18006B320
0x18006b306  mov     rcx, cs:gRegHelpEtwContext
0x18006b30d  lea     r8, aDwmarkinterfac_3; "DwMarkInterfaceKeyAsVPN : Failed to set"...
0x18006b314  mov     rax, cs:gRegHelpTemplateFunc
0x18006b31b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b320  mov     rcx, [rsp+278h+hKey]; hKey
0x18006b325  call    cs:__imp_RegCloseKey
0x18006b32b  jmp     short loc_18006B361
0x18006b32d  lea     rdx, aDwmarkinterfac_6; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x18006b334  mov     ecx, edi; unsigned int
0x18006b336  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006b33b  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006b342  test    rdx, rdx
0x18006b345  jz      short loc_18006B361
0x18006b347  lea     r8, aDwmarkinterfac_2; "DwMarkInterfaceKeyAsVPN : Failed to Ope"...
0x18006b34e  mov     rcx, cs:gRegHelpEtwContext
0x18006b355  mov     rax, cs:gRegHelpTemplateFunc
0x18006b35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b361  mov     eax, ebx
0x18006b363  mov     rcx, [rsp+278h+var_28]
0x18006b36b  xor     rcx, rsp; StackCookie
0x18006b36e  call    __security_check_cookie
0x18006b373  add     rsp, 260h
0x18006b37a  pop     rdi
0x18006b37b  pop     rsi
0x18006b37c  pop     rbx
0x18006b37d  retn
```
