# SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)

- ea: `0x180023660`
- end: `0x1800237ac`
- name: `?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z`
- size: `332`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpValueName, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ffb4`

## callees

- `0x1800039f0`
- `0x18000c504`
- `0x180023660`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180023690`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180023690`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002377c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002377c`

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
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1);
  v7 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v7 = &word_1800401D0;
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
0x180023660  push    rbx
0x180023662  push    rbp
0x180023663  push    rsi
0x180023664  push    rdi
0x180023665  push    r14
0x180023667  sub     rsp, 110h
0x18002366e  mov     rax, cs:__security_cookie
0x180023675  xor     rax, rsp
0x180023678  mov     [rsp+138h+var_38], rax
0x180023680  mov     rsi, rdx
0x180023683  mov     [rsp+138h+Data], r8d
0x180023688  mov     rdi, rcx
0x18002368b  mov     ebx, 7FFFFFFEh
0x180023690  call    cs:__imp_RtlIsStateSeparationEnabled
0x180023696  xor     ebp, ebp
0x180023698  lea     rcx, word_1800401D0
0x18002369f  test    al, al
0x1800236a1  lea     rdx, aOsdata; "OSData\\"
0x1800236a8  cmovz   rdx, rcx
0x1800236ac  lea     rcx, [rsp+138h+SubKey]
0x1800236b1  lea     r14d, [rbp+60h]
0x1800236b5  mov     r8d, r14d
0x1800236b8  test    rbx, rbx
0x1800236bb  jz      short loc_1800236D9
0x1800236bd  movzx   eax, word ptr [rdx]
0x1800236c0  test    ax, ax
0x1800236c3  jz      short loc_1800236D9
0x1800236c5  mov     [rcx], ax
0x1800236c8  add     rdx, 2
0x1800236cc  add     rcx, 2
0x1800236d0  dec     rbx
0x1800236d3  sub     r8, 1
0x1800236d7  jnz     short loc_1800236B8
0x1800236d9  mov     rax, r8
0x1800236dc  lea     rdx, [rcx-2]
0x1800236e0  neg     rax
0x1800236e3  sbb     eax, eax
0x1800236e5  not     eax
0x1800236e7  and     eax, 8007007Ah
0x1800236ec  test    r8, r8
0x1800236ef  cmovnz  rdx, rcx
0x1800236f3  mov     [rdx], bp
0x1800236f6  jz      loc_18002378E
0x1800236fc  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x180023703  mov     rdx, r14; unsigned __int64
0x180023706  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18002370b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023710  test    eax, eax
0x180023712  js      short loc_18002378E
0x180023714  mov     r8, rdi; unsigned __int16 *
0x180023717  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18002371c  mov     rdx, r14; unsigned __int64
0x18002371f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023724  test    eax, eax
0x180023726  js      short loc_18002378E
0x180023728  lea     r8, StringValue; "\\"
0x18002372f  mov     rdx, r14; unsigned __int64
0x180023732  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x180023737  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002373c  test    eax, eax
0x18002373e  js      short loc_18002378E
0x180023740  lea     r8, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x180023747  mov     rdx, r14; unsigned __int64
0x18002374a  lea     rcx, [rsp+138h+SubKey]; unsigned __int16 *
0x18002374f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023754  test    eax, eax
0x180023756  js      short loc_18002378E
0x180023758  mov     r9d, 4; dwType
0x18002375e  lea     rax, [rsp+138h+Data]
0x180023763  mov     [rsp+138h+cbData], r9d; cbData
0x180023768  lea     rdx, [rsp+138h+SubKey]; lpSubKey
0x18002376d  mov     r8, rsi; lpValueName
0x180023770  mov     [rsp+138h+lpData], rax; lpData
0x180023775  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002377c  call    cs:__imp_RegSetKeyValueW
0x180023782  test    eax, eax
0x180023784  jle     short loc_18002378E
0x180023786  movzx   eax, ax
0x180023789  or      eax, 80070000h
0x18002378e  mov     rcx, [rsp+138h+var_38]
0x180023796  xor     rcx, rsp; StackCookie
0x180023799  call    __security_check_cookie
0x18002379e  add     rsp, 110h
0x1800237a5  pop     r14
0x1800237a7  pop     rdi
0x1800237a8  pop     rsi
0x1800237a9  pop     rbp
0x1800237aa  pop     rbx
0x1800237ab  retn
```
