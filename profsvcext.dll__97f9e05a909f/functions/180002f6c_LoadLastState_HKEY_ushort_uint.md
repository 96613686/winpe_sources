# LoadLastState(HKEY__ *,ushort * *,uint &)

- ea: `0x180002f6c`
- end: `0x18000307b`
- name: `?LoadLastState@@YAJPEAUHKEY__@@PEAPEAGAEAI@Z`
- size: `271`
- prototype: `LSTATUS __fastcall(HKEY, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`
- `0x180005b54`

## callees

- `0x180002f6c`
- `0x18000a520`
- `0x18001e520`
- `0x18001e580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000300f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000300f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fd0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002fd0`

## pseudocode

```c
LSTATUS __fastcall LoadLastState(HKEY a1, unsigned __int16 **a2, unsigned int *a3)
{
  LSTATUS result; // eax
  DWORD v6; // ebx
  unsigned __int16 *v7; // rax
  size_t v8; // r8
  DWORD cbData; // [rsp+30h] [rbp-2038h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-2034h] BYREF
  BYTE Data[2]; // [rsp+40h] [rbp-2028h] BYREF

  cbData = 0x2000;
  *a2 = 0;
  *a3 = 0;
  Type[0] = 0;
  result = RegQueryValueExW(a1, L"CscSuspendedDirs", 0, Type, Data, &cbData);
  if ( result )
  {
    if ( result == 2 )
    {
      return 0;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    if ( Type[0] != 7 )
      return -2147467259;
    if ( (cbData & 1) != 0 )
      return -2147467259;
    v6 = cbData >> 1;
    if ( !(cbData >> 1) || *(_WORD *)&Data[2 * v6 - 2] || v6 >= 2 && *(_WORD *)&Data[2 * v6 - 4] )
    {
      return -2147467259;
    }
    else
    {
      v7 = (unsigned __int16 *)CoTaskMemAlloc(cbData);
      *a2 = v7;
      if ( v7 )
      {
        v8 = cbData;
        *a3 = v6;
        memcpy_0(*a2, Data, v8);
        return 0;
      }
      else
      {
        return -2147024882;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002f6c  mov     [rsp+arg_18], rbx
0x180002f71  push    rbp
0x180002f72  push    rsi
0x180002f73  push    rdi
0x180002f74  mov     eax, 2050h
0x180002f79  call    _alloca_probe
0x180002f7e  sub     rsp, rax
0x180002f81  mov     rax, cs:__security_cookie
0x180002f88  xor     rax, rsp
0x180002f8b  mov     [rsp+2068h+var_28], rax
0x180002f93  xor     ebp, ebp
0x180002f95  mov     [rsp+2068h+cbData], 2000h
0x180002f9d  mov     [rdx], rbp
0x180002fa0  lea     rax, [rsp+2068h+cbData]
0x180002fa5  mov     [rsp+2068h+lpcbData], rax; lpcbData
0x180002faa  lea     r9, [rsp+2068h+Type]; lpType
0x180002faf  mov     [r8], ebp
0x180002fb2  lea     rax, [rsp+2068h+Data]
0x180002fb7  mov     rsi, r8
0x180002fba  mov     [rsp+2068h+lpData], rax; lpData
0x180002fbf  mov     rdi, rdx
0x180002fc2  mov     [rsp+2068h+Type], ebp
0x180002fc6  xor     r8d, r8d; lpReserved
0x180002fc9  lea     rdx, ValueName; "CscSuspendedDirs"
0x180002fd0  call    cs:__imp_RegQueryValueExW
0x180002fd6  test    eax, eax
0x180002fd8  jnz     short loc_180003043
0x180002fda  cmp     [rsp+2068h+Type], 7
0x180002fdf  jnz     short loc_18000303C
0x180002fe1  mov     r8d, [rsp+2068h+cbData]
0x180002fe6  test    r8b, 1
0x180002fea  jnz     short loc_18000303C
0x180002fec  mov     ebx, r8d
0x180002fef  shr     ebx, 1
0x180002ff1  jz      short loc_18000303C
0x180002ff3  lea     eax, [rbx-1]
0x180002ff6  cmp     word ptr [rsp+rax*2+2068h+Data], bp
0x180002ffb  jnz     short loc_18000303C
0x180002ffd  cmp     ebx, 2
0x180003000  jb      short loc_18000300C
0x180003002  lea     eax, [rbx-2]
0x180003005  cmp     word ptr [rsp+rax*2+2068h+Data], bp
0x18000300a  jnz     short loc_18000303C
0x18000300c  mov     rcx, r8; cb
0x18000300f  call    cs:__imp_CoTaskMemAlloc
0x180003015  mov     [rdi], rax
0x180003018  test    rax, rax
0x18000301b  jz      short loc_180003035
0x18000301d  mov     r8d, [rsp+2068h+cbData]; Size
0x180003022  lea     rdx, [rsp+2068h+Data]; Src
0x180003027  mov     [rsi], ebx
0x180003029  mov     rcx, [rdi]; void *
0x18000302c  call    memcpy_0
0x180003031  mov     eax, ebp
0x180003033  jmp     short loc_180003058
0x180003035  mov     eax, 8007000Eh
0x18000303a  jmp     short loc_180003058
0x18000303c  mov     eax, 80004005h
0x180003041  jmp     short loc_180003058
0x180003043  cmp     eax, 2
0x180003046  jnz     short loc_18000304C
0x180003048  xor     eax, eax
0x18000304a  jmp     short loc_180003058
0x18000304c  test    eax, eax
0x18000304e  jle     short loc_180003058
0x180003050  movzx   eax, ax
0x180003053  or      eax, 80070000h
0x180003058  mov     rcx, [rsp+2068h+var_28]
0x180003060  xor     rcx, rsp; StackCookie
0x180003063  call    __security_check_cookie
0x180003068  mov     rbx, [rsp+2068h+arg_18]
0x180003070  add     rsp, 2050h
0x180003077  pop     rdi
0x180003078  pop     rsi
0x180003079  pop     rbp
0x18000307a  retn
```
