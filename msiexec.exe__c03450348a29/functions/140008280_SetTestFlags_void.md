# SetTestFlags(void)

- ea: `0x140008280`
- end: `0x1400082fa`
- name: `?SetTestFlags@@YA_NXZ`
- size: `122`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400078f0`

## callees

- `0x140008280`
- `0x140009820`

## import_xrefs

- `KERNEL32!GetEnvironmentVariableW` at `0x1400082ab`
- `KERNEL32!GetEnvironmentVariableW` at `0x1400082ab`

## string_xrefs

- `0x1400082a4`: `_MSI_TEST`

## pseudocode

```c
bool SetTestFlags(void)
{
  DWORD EnvironmentVariableW; // eax
  int v1; // eax
  char *v2; // rdx
  int v3; // ecx
  WCHAR Buffer; // [rsp+20h] [rbp-98h] BYREF
  char v6; // [rsp+22h] [rbp-96h] BYREF

  EnvironmentVariableW = GetEnvironmentVariableW(L"_MSI_TEST", &Buffer, 0x40u);
  if ( EnvironmentVariableW )
  {
    LOBYTE(v1) = Buffer;
    v2 = &v6;
    if ( Buffer )
    {
      v3 = g_iTestFlags;
      do
      {
        v3 |= 1 << (v1 & 0x1F);
        v1 = *(unsigned __int16 *)v2;
        v2 += 2;
      }
      while ( v1 );
      g_iTestFlags = v3;
    }
    LOBYTE(EnvironmentVariableW) = 1;
  }
  return EnvironmentVariableW;
}

```

## disassembly

```asm
0x140008280  sub     rsp, 0B8h
0x140008287  mov     rax, cs:__security_cookie
0x14000828e  xor     rax, rsp
0x140008291  mov     [rsp+0B8h+var_18], rax
0x140008299  mov     r8d, 40h ; '@'; nSize
0x14000829f  lea     rdx, [rsp+0B8h+Buffer]; lpBuffer
0x1400082a4  lea     rcx, Name; "_MSI_TEST"
0x1400082ab  call    cs:__imp_GetEnvironmentVariableW
0x1400082b1  test    eax, eax
0x1400082b3  jz      short loc_1400082E2
0x1400082b5  movzx   eax, [rsp+0B8h+Buffer]
0x1400082ba  lea     rdx, [rsp+0B8h+var_96]
0x1400082bf  test    eax, eax
0x1400082c1  jz      short loc_1400082E0
0x1400082c3  mov     ecx, cs:?g_iTestFlags@@3HA; int g_iTestFlags
0x1400082c9  and     eax, 1Fh
0x1400082cc  bts     ecx, eax
0x1400082cf  movzx   eax, word ptr [rdx]
0x1400082d2  lea     rdx, [rdx+2]
0x1400082d6  test    eax, eax
0x1400082d8  jnz     short loc_1400082C9
0x1400082da  mov     cs:?g_iTestFlags@@3HA, ecx; int g_iTestFlags
0x1400082e0  mov     al, 1
0x1400082e2  mov     rcx, [rsp+0B8h+var_18]
0x1400082ea  xor     rcx, rsp; StackCookie
0x1400082ed  call    __security_check_cookie
0x1400082f2  add     rsp, 0B8h
0x1400082f9  retn
```
