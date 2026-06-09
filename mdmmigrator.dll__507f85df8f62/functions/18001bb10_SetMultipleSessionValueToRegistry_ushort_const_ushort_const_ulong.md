# SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x18001bb10`
- end: `0x18001bc5c`
- name: `?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z`
- size: `332`
- prototype: `LSTATUS __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c61c`

## callees

- `0x1800022e0`
- `0x180006bd4`
- `0x18001bb10`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x18001bb40`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001bb40`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bc2c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bc2c`

## pseudocode

```c
LSTATUS __fastcall SetMultipleSessionValueToRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  __int64 v5; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rdx
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rdx
  LSTATUS result; // eax
  _DWORD Data[4]; // [rsp+30h] [rbp-108h] BYREF
  WCHAR SubKey[96]; // [rsp+40h] [rbp-F8h] BYREF

  Data[0] = a3;
  v5 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, lpValueName);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &dword_18002237C;
  v8 = SubKey;
  v9 = 96;
  do
  {
    if ( !v5 )
      break;
    if ( !*v7 )
      break;
    *v8++ = *v7++;
    --v5;
    --v9;
  }
  while ( v9 );
  v10 = v8 - 1;
  result = v9 == 0 ? 0x8007007A : 0;
  if ( v9 )
    v10 = v8;
  *v10 = 0;
  if ( v9 )
  {
    result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x60u, a1);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x60u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x60u, c_szEnrollmentsDBMultipleSession);
          if ( result >= 0 )
          {
            result = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, lpValueName, 4u, Data, 4u);
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001bb10  push    rbx
0x18001bb12  push    rbp
0x18001bb13  push    rsi
0x18001bb14  push    rdi
0x18001bb15  push    r14
0x18001bb17  sub     rsp, 110h
0x18001bb1e  mov     rax, cs:__security_cookie
0x18001bb25  xor     rax, rsp
0x18001bb28  mov     [rsp+138h+var_38], rax
0x18001bb30  mov     rsi, rdx
0x18001bb33  mov     [rsp+138h+Data], r8d
0x18001bb38  mov     rdi, rcx
0x18001bb3b  mov     ebx, 7FFFFFFEh
0x18001bb40  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001bb46  xor     ebp, ebp
0x18001bb48  lea     rcx, dword_18002237C
0x18001bb4f  test    al, al
0x18001bb51  lea     rdx, aOsdata; "OSData\\"
0x18001bb58  cmovz   rdx, rcx
0x18001bb5c  lea     rcx, [rsp+138h+SubKey]
0x18001bb61  lea     r14d, [rbp+60h]
0x18001bb65  mov     r8d, r14d
0x18001bb68  test    rbx, rbx
0x18001bb6b  jz      short loc_18001BB89
0x18001bb6d  movzx   eax, word ptr [rdx]
0x18001bb70  test    ax, ax
0x18001bb73  jz      short loc_18001BB89
0x18001bb75  mov     [rcx], ax
0x18001bb78  add     rdx, 2
0x18001bb7c  add     rcx, 2
0x18001bb80  dec     rbx
0x18001bb83  sub     r8, 1
0x18001bb87  jnz     short loc_18001BB68
0x18001bb89  mov     rax, r8
0x18001bb8c  lea     rdx, [rcx-2]
0x18001bb90  neg     rax
0x18001bb93  sbb     eax, eax
0x18001bb95  not     eax
0x18001bb97  and     eax, 8007007Ah
0x18001bb9c  test    r8, r8
0x18001bb9f  cmovnz  rdx, rcx
0x18001bba3  mov     [rdx], bp
0x18001bba6  jz      loc_18001BC3E
0x18001bbac  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x18001bbb3  mov     rdx, r14; unsigned __int64
0x18001bbb6  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18001bbbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bbc0  test    eax, eax
0x18001bbc2  js      short loc_18001BC3E
0x18001bbc4  mov     r8, rdi; unsigned __int16 *
0x18001bbc7  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18001bbcc  mov     rdx, r14; unsigned __int64
0x18001bbcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bbd4  test    eax, eax
0x18001bbd6  js      short loc_18001BC3E
0x18001bbd8  lea     r8, asc_180021D44; "\\"
0x18001bbdf  mov     rdx, r14; unsigned __int64
0x18001bbe2  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18001bbe7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bbec  test    eax, eax
0x18001bbee  js      short loc_18001BC3E
0x18001bbf0  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x18001bbf7  mov     rdx, r14; unsigned __int64
0x18001bbfa  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18001bbff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bc04  test    eax, eax
0x18001bc06  js      short loc_18001BC3E
0x18001bc08  mov     r9d, 4; dwType
0x18001bc0e  lea     rax, [rsp+138h+Data]
0x18001bc13  mov     [rsp+138h+cbData], r9d; cbData
0x18001bc18  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18001bc1d  mov     r8, rsi; lpValueName
0x18001bc20  mov     [rsp+138h+lpData], rax; lpData
0x18001bc25  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bc2c  call    cs:__imp_RegSetKeyValueW
0x18001bc32  test    eax, eax
0x18001bc34  jle     short loc_18001BC3E
0x18001bc36  movzx   eax, ax
0x18001bc39  or      eax, 80070000h
0x18001bc3e  mov     rcx, [rsp+138h+var_38]
0x18001bc46  xor     rcx, rsp; StackCookie
0x18001bc49  call    __security_check_cookie
0x18001bc4e  add     rsp, 110h
0x18001bc55  pop     r14
0x18001bc57  pop     rdi
0x18001bc58  pop     rsi
0x18001bc59  pop     rbp
0x18001bc5a  pop     rbx
0x18001bc5b  retn
```
