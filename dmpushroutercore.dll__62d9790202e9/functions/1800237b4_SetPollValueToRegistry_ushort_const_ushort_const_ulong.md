# SetPollValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x1800237b4`
- end: `0x180023900`
- name: `?SetPollValueToRegistry@@YAJPEBG0K@Z`
- size: `332`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f5fc`

## callees

- `0x1800039f0`
- `0x18000c504`
- `0x1800237b4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800237e4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800237e4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800238d0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800238d0`

## pseudocode

```c
LSTATUS __fastcall SetPollValueToRegistry(const unsigned __int16 *a1, LPCWSTR lpValueName, int a3)
{
  __int64 v5; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v7; // rdx
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rdx
  LSTATUS result; // eax
  _DWORD Data[4]; // [rsp+30h] [rbp-F8h] BYREF
  WCHAR SubKey[88]; // [rsp+40h] [rbp-E8h] BYREF

  Data[0] = a3;
  v5 = 2147483646;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &word_1800401D0;
  v8 = SubKey;
  v9 = 85;
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
    result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDB);
    if ( result >= 0 )
    {
      result = StringCchCatW(SubKey, 0x55u, a1);
      if ( result >= 0 )
      {
        result = StringCchCatW(SubKey, 0x55u, L"\\");
        if ( result >= 0 )
        {
          result = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDBPoll);
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
0x1800237b4  push    rbx
0x1800237b6  push    rbp
0x1800237b7  push    rsi
0x1800237b8  push    rdi
0x1800237b9  push    r14
0x1800237bb  sub     rsp, 100h
0x1800237c2  mov     rax, cs:__security_cookie
0x1800237c9  xor     rax, rsp
0x1800237cc  mov     [rsp+128h+var_38], rax
0x1800237d4  mov     rsi, rdx
0x1800237d7  mov     [rsp+128h+Data], r8d
0x1800237dc  mov     rdi, rcx
0x1800237df  mov     ebx, 7FFFFFFEh
0x1800237e4  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800237ea  xor     ebp, ebp
0x1800237ec  lea     rcx, word_1800401D0
0x1800237f3  test    al, al
0x1800237f5  lea     rdx, aOsdata; "OSData\\"
0x1800237fc  cmovz   rdx, rcx
0x180023800  lea     rcx, [rsp+128h+SubKey]
0x180023805  lea     r14d, [rbp+55h]
0x180023809  mov     r8d, r14d
0x18002380c  test    rbx, rbx
0x18002380f  jz      short loc_18002382D
0x180023811  movzx   eax, word ptr [rdx]
0x180023814  test    ax, ax
0x180023817  jz      short loc_18002382D
0x180023819  mov     [rcx], ax
0x18002381c  add     rdx, 2
0x180023820  add     rcx, 2
0x180023824  dec     rbx
0x180023827  sub     r8, 1
0x18002382b  jnz     short loc_18002380C
0x18002382d  mov     rax, r8
0x180023830  lea     rdx, [rcx-2]
0x180023834  neg     rax
0x180023837  sbb     eax, eax
0x180023839  not     eax
0x18002383b  and     eax, 8007007Ah
0x180023840  test    r8, r8
0x180023843  cmovnz  rdx, rcx
0x180023847  mov     [rdx], bp
0x18002384a  jz      loc_1800238E2
0x180023850  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x180023857  mov     rdx, r14; unsigned __int64
0x18002385a  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18002385f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023864  test    eax, eax
0x180023866  js      short loc_1800238E2
0x180023868  mov     r8, rdi; unsigned __int16 *
0x18002386b  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x180023870  mov     rdx, r14; unsigned __int64
0x180023873  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023878  test    eax, eax
0x18002387a  js      short loc_1800238E2
0x18002387c  lea     r8, StringValue; "\\"
0x180023883  mov     rdx, r14; unsigned __int64
0x180023886  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x18002388b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023890  test    eax, eax
0x180023892  js      short loc_1800238E2
0x180023894  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x18002389b  mov     rdx, r14; unsigned __int64
0x18002389e  lea     rcx, [rsp+128h+SubKey]; unsigned __int16 *
0x1800238a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800238a8  test    eax, eax
0x1800238aa  js      short loc_1800238E2
0x1800238ac  mov     r9d, 4; dwType
0x1800238b2  lea     rax, [rsp+128h+Data]
0x1800238b7  mov     [rsp+128h+cbData], r9d; cbData
0x1800238bc  lea     rdx, [rsp+128h+SubKey]; lpSubKey
0x1800238c1  mov     r8, rsi; lpValueName
0x1800238c4  mov     [rsp+128h+lpData], rax; lpData
0x1800238c9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800238d0  call    cs:__imp_RegSetKeyValueW
0x1800238d6  test    eax, eax
0x1800238d8  jle     short loc_1800238E2
0x1800238da  movzx   eax, ax
0x1800238dd  or      eax, 80070000h
0x1800238e2  mov     rcx, [rsp+128h+var_38]
0x1800238ea  xor     rcx, rsp; StackCookie
0x1800238ed  call    __security_check_cookie
0x1800238f2  add     rsp, 100h
0x1800238f9  pop     r14
0x1800238fb  pop     rdi
0x1800238fc  pop     rsi
0x1800238fd  pop     rbp
0x1800238fe  pop     rbx
0x1800238ff  retn
```
