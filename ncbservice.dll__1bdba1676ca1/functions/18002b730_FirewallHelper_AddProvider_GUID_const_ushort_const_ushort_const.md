# FirewallHelper::AddProvider(_GUID const &,ushort const *,ushort const *)

- ea: `0x18002b730`
- end: `0x18002b89c`
- name: `?AddProvider@FirewallHelper@@YAJAEBU_GUID@@PEBG1@Z`
- size: `364`
- prototype: `__int64 __fastcall(GUID *key, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029a60`

## callees

- `0x18001c080`
- `0x18001d8e0`
- `0x18002b730`

## import_xrefs

- `fwpuclnt!FwpmProviderGetByKey0` at `0x18002b7bc`
- `fwpuclnt!FwpmProviderGetByKey0` at `0x18002b7bc`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002b778`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002b778`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002b865`
- `fwpuclnt!FwpmFreeMemory0` at `0x18002b865`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b82d`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b83a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b856`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b86e`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b82d`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b83a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b856`
- `fwpuclnt!FwpmEngineClose0` at `0x18002b86e`
- `fwpuclnt!FwpmProviderAdd0` at `0x18002b802`
- `fwpuclnt!FwpmProviderAdd0` at `0x18002b802`

## pseudocode

```c
int __fastcall FirewallHelper::AddProvider(GUID *key, wchar_t *a2, wchar_t *a3, const unsigned __int16 *a4)
{
  DWORD v7; // eax
  int result; // eax
  unsigned int v9; // r8d
  const char *v10; // r9
  HANDLE v11; // rdi
  signed int v12; // eax
  unsigned int v13; // ebx
  DWORD v14; // eax
  int v15; // ebx
  unsigned int engineHandle; // [rsp+20h] [rbp-98h]
  HANDLE v17; // [rsp+30h] [rbp-88h] BYREF
  FWPM_PROVIDER0 *provider; // [rsp+38h] [rbp-80h] BYREF
  FWPM_PROVIDER0 v19; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v17 = 0;
  v7 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &v17);
  if ( v7 )
  {
    result = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x20F,
               (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
               (const char *)v7,
               engineHandle);
  }
  else
  {
    v11 = v17;
    provider = 0;
    v12 = FwpmProviderGetByKey0(v17, key, &provider);
    v13 = v12;
    if ( v12 == -2144206843 )
    {
      memset(&v19.providerKey.Data2, 0, 60);
      v19.providerKey = *key;
      v19.displayData.name = a2;
      v19.displayData.description = a3;
      v14 = FwpmProviderAdd0(v17, &v19, 0);
      if ( v14 )
      {
        v15 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x21C,
                (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
                (const char *)v14,
                engineHandle);
        FwpmEngineClose0(v11);
        result = v15;
      }
      else
      {
        FwpmEngineClose0(v11);
        result = 0;
      }
    }
    else if ( v12 )
    {
      if ( v12 > 0 )
        v13 = (unsigned __int16)v12 | 0x80070000;
      FwpmEngineClose0(v11);
      result = v13;
    }
    else
    {
      FwpmFreeMemory0((void **)&provider);
      FwpmEngineClose0(v11);
      result = 0;
    }
  }
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x227, v9, v10);
      result = (int)v17;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18002b730  push    rbx
0x18002b732  push    rsi
0x18002b733  push    rdi
0x18002b734  push    r14
0x18002b736  push    r15
0x18002b738  sub     rsp, 90h
0x18002b73f  mov     rax, cs:__security_cookie
0x18002b746  xor     rax, rsp
0x18002b749  mov     [rsp+0B8h+var_38], rax
0x18002b751  mov     r15, r8
0x18002b754  mov     r14, rdx
0x18002b757  mov     rsi, rcx
0x18002b75a  mov     [rsp+0B8h+var_88], 0
0x18002b763  lea     rax, [rsp+0B8h+var_88]
0x18002b768  mov     qword ptr [rsp+0B8h+engineHandle], rax; unsigned int
0x18002b76d  xor     r9d, r9d; session
0x18002b770  xor     r8d, r8d; authIdentity
0x18002b773  or      edx, 0FFFFFFFFh; authnService
0x18002b776  xor     ecx, ecx; serverName
0x18002b778  call    cs:__imp_FwpmEngineOpen0
0x18002b77e  test    eax, eax
0x18002b780  jz      short loc_18002B7A3
0x18002b782  mov     rcx, [rsp+0B8h]; this
0x18002b78a  mov     r9d, eax; char *
0x18002b78d  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b794  mov     edx, 20Fh; void *
0x18002b799  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b79e  jmp     loc_18002B87C
0x18002b7a3  mov     rdi, [rsp+0B8h+var_88]
0x18002b7a8  mov     [rsp+0B8h+provider], 0
0x18002b7b1  lea     r8, [rsp+0B8h+provider]; provider
0x18002b7b6  mov     rdx, rsi; key
0x18002b7b9  mov     rcx, rdi; engineHandle
0x18002b7bc  call    cs:__imp_FwpmProviderGetByKey0
0x18002b7c2  mov     ebx, eax
0x18002b7c4  cmp     eax, 80320005h
0x18002b7c9  jnz     short loc_18002B844
0x18002b7cb  xorps   xmm0, xmm0
0x18002b7ce  movups  xmmword ptr [rsp+0B8h+var_78.providerKey.Data2], xmm0
0x18002b7d3  movups  xmmword ptr [rsp+0B8h+var_78.displayData.name+4], xmm0
0x18002b7d8  movups  xmmword ptr [rsp+0B8h+var_78+24h], xmm0
0x18002b7dd  movups  xmmword ptr [rsp+0B8h+var_78.providerData.data], xmm0
0x18002b7e2  movups  xmm0, xmmword ptr [rsi]
0x18002b7e5  movdqu  xmmword ptr [rsp+40h], xmm0
0x18002b7eb  mov     [rsp+0B8h+var_78.displayData.name], r14
0x18002b7f0  mov     [rsp+0B8h+var_78.displayData.description], r15
0x18002b7f5  xor     r8d, r8d; sd
0x18002b7f8  lea     rdx, [rsp+0B8h+var_78]; provider
0x18002b7fd  mov     rcx, [rsp+0B8h+var_88]; engineHandle
0x18002b802  call    cs:__imp_FwpmProviderAdd0
0x18002b808  test    eax, eax
0x18002b80a  jz      short loc_18002B837
0x18002b80c  mov     rcx, [rsp+0B8h]; this
0x18002b814  mov     r9d, eax; char *
0x18002b817  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002b81e  mov     edx, 21Ch; void *
0x18002b823  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002b828  mov     ebx, eax
0x18002b82a  mov     rcx, rdi; engineHandle
0x18002b82d  call    cs:__imp_FwpmEngineClose0
0x18002b833  mov     eax, ebx
0x18002b835  jmp     short loc_18002B87C
0x18002b837  mov     rcx, rdi; engineHandle
0x18002b83a  call    cs:__imp_FwpmEngineClose0
0x18002b840  xor     eax, eax
0x18002b842  jmp     short loc_18002B87C
0x18002b844  test    eax, eax
0x18002b846  jz      short loc_18002B860
0x18002b848  jle     short loc_18002B853
0x18002b84a  movzx   ebx, ax
0x18002b84d  or      ebx, 80070000h
0x18002b853  mov     rcx, rdi; engineHandle
0x18002b856  call    cs:__imp_FwpmEngineClose0
0x18002b85c  mov     eax, ebx
0x18002b85e  jmp     short loc_18002B87C
0x18002b860  lea     rcx, [rsp+0B8h+provider]; p
0x18002b865  call    cs:__imp_FwpmFreeMemory0
0x18002b86b  mov     rcx, rdi; engineHandle
0x18002b86e  call    cs:__imp_FwpmEngineClose0
0x18002b874  xor     eax, eax
0x18002b876  jmp     short loc_18002B87C
0x18002b878  mov     eax, dword ptr [rsp+0B8h+var_88]
0x18002b87c  mov     rcx, [rsp+0B8h+var_38]
0x18002b884  xor     rcx, rsp; StackCookie
0x18002b887  call    __security_check_cookie
0x18002b88c  add     rsp, 90h
0x18002b893  pop     r15
0x18002b895  pop     r14
0x18002b897  pop     rdi
0x18002b898  pop     rsi
0x18002b899  pop     rbx
0x18002b89a  retn
```
