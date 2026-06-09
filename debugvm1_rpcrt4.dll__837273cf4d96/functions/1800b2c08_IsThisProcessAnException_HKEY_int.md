# IsThisProcessAnException(HKEY__ *,int *)

- ea: `0x1800b2c08`
- end: `0x1800b2e12`
- name: `?IsThisProcessAnException@@YAJPEAUHKEY__@@PEAH@Z`
- size: `522`
- prototype: `__int64 __fastcall(HKEY hkey, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180091010`

## callees

- `0x180021e70`
- `0x180022870`
- `0x1800b2a70`
- `0x1800b2c08`

## import_xrefs

- `ntdll!wcsrchr` at `0x1800b2d08`
- `ntdll!wcsrchr` at `0x1800b2d08`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2c6d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2c6d`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b2cf7`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800b2cf7`

## pseudocode

```c
__int64 __fastcall IsThisProcessAnException(HKEY hkey, int *a2)
{
  unsigned int v4; // edi
  void *pvData; // rbp
  int i; // r15d
  LSTATUS ValueW; // eax
  __int64 result; // rax
  const wchar_t *CommandLineW; // rbx
  wchar_t *v10; // rax
  int v11; // ecx
  unsigned __int16 *v12; // rsi
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // rbx
  DWORD pcbData; // [rsp+98h] [rbp+10h] BYREF

  pcbData = 0;
  v4 = 0;
  *a2 = 0;
  pvData = 0;
  for ( i = 5; ; --i )
  {
    if ( i <= 0 )
      goto LABEL_11;
    ValueW = RegGetValueW(hkey, 0, L"ExtErrorInfoExceptions", 2u, 0, pvData, &pcbData);
    v4 = ValueW;
    if ( ValueW && ValueW != 234 )
    {
      v4 = ValueW != 2 ? 0xE : 0;
LABEL_11:
      if ( pvData )
        goto LABEL_12;
      goto LABEL_13;
    }
    if ( pvData )
      break;
LABEL_8:
    pvData = AllocWrapper(saturated_mul(pcbData, 2u));
    if ( !pvData )
      return 14;
  }
  if ( ValueW == 234 )
  {
    FreeWrapper(pvData);
    goto LABEL_8;
  }
  CommandLineW = GetCommandLineW();
  v10 = wcsrchr(CommandLineW, 0x5Cu);
  v11 = 0;
  v12 = 0;
  v13 = v10 + 1;
  if ( !v10 )
    v13 = (unsigned __int16 *)CommandLineW;
  v14 = (unsigned __int16 *)pvData;
  while ( 2 )
  {
    if ( *v14 )
    {
      if ( v11 )
      {
        if ( v11 == 1 )
        {
          if ( *v14 == 34 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
            v11 = 0;
          }
          goto LABEL_35;
        }
        if ( v11 != 2 )
        {
          if ( *v14 == 34 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
            v12 = v14 + 1;
            goto LABEL_34;
          }
          if ( *v14 == 32 )
          {
            *v14 = 0;
            if ( (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
              goto LABEL_28;
LABEL_34:
            v11 = 3;
          }
LABEL_35:
          ++v14;
          continue;
        }
        if ( *v14 == 34 )
        {
          v12 = v14 + 1;
LABEL_31:
          v11 = 1;
          goto LABEL_35;
        }
        if ( *v14 == 32 )
          goto LABEL_35;
      }
      else
      {
        if ( *v14 == 34 )
        {
          v12 = v14;
          goto LABEL_31;
        }
        if ( *v14 == 32 )
        {
          v11 = 2;
          goto LABEL_35;
        }
      }
      v12 = v14;
      goto LABEL_34;
    }
    break;
  }
  if ( v12 && (unsigned int)DoesThisProcessCmdLineStartWithThisString(v13, v12) )
LABEL_28:
    *a2 = 1;
LABEL_12:
  FreeWrapper(pvData);
LABEL_13:
  result = v4;
  if ( !i )
    return 1766;
  return result;
}

```

## disassembly

```asm
0x1800b2c08  mov     rax, rsp
0x1800b2c0b  push    rbx
0x1800b2c0c  push    rbp
0x1800b2c0d  push    rsi
0x1800b2c0e  push    rdi
0x1800b2c0f  push    r12
0x1800b2c11  push    r13
0x1800b2c13  push    r14
0x1800b2c15  push    r15
0x1800b2c17  sub     rsp, 48h
0x1800b2c1b  xor     r13d, r13d
0x1800b2c1e  mov     r14, rdx
0x1800b2c21  mov     rbx, rcx
0x1800b2c24  mov     [rax+10h], r13d
0x1800b2c28  mov     edi, r13d
0x1800b2c2b  mov     [rdx], r13d
0x1800b2c2e  mov     ebp, r13d
0x1800b2c31  mov     esi, 0EAh
0x1800b2c36  lea     r15d, [r13+5]
0x1800b2c3a  lea     r12d, [r13+2]
0x1800b2c3e  test    r15d, r15d
0x1800b2c41  jle     loc_1800B2CCC
0x1800b2c47  lea     rax, [rsp+88h+arg_8]
0x1800b2c4f  mov     r9d, r12d; dwFlags
0x1800b2c52  mov     [rsp+88h+pcbData], rax; pcbData
0x1800b2c57  lea     r8, aExterrorinfoex; "ExtErrorInfoExceptions"
0x1800b2c5e  mov     [rsp+88h+pvData], rbp; pvData
0x1800b2c63  xor     edx, edx; lpSubKey
0x1800b2c65  mov     rcx, rbx; hkey
0x1800b2c68  mov     [rsp+88h+pdwType], r13; pdwType
0x1800b2c6d  call    cs:__imp_RegGetValueW
0x1800b2c73  mov     edi, eax
0x1800b2c75  test    eax, eax
0x1800b2c77  jz      short loc_1800B2C7D
0x1800b2c79  cmp     eax, esi
0x1800b2c7b  jnz     short loc_1800B2CC2
0x1800b2c7d  test    rbp, rbp
0x1800b2c80  jz      short loc_1800B2C8E
0x1800b2c82  cmp     edi, esi
0x1800b2c84  jnz     short loc_1800B2CF7
0x1800b2c86  mov     rcx, rbp; lpMem
0x1800b2c89  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b2c8e  mov     ecx, [rsp+88h+arg_8]
0x1800b2c95  mov     rax, r12
0x1800b2c98  mul     rcx
0x1800b2c9b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b2ca2  cmovb   rax, rcx
0x1800b2ca6  mov     rcx, rax; dwBytes
0x1800b2ca9  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x1800b2cae  mov     rbp, rax
0x1800b2cb1  test    rax, rax
0x1800b2cb4  jz      loc_1800B2E08
0x1800b2cba  dec     r15d
0x1800b2cbd  jmp     loc_1800B2C3E
0x1800b2cc2  sub     edi, r12d
0x1800b2cc5  neg     edi
0x1800b2cc7  sbb     edi, edi
0x1800b2cc9  and     edi, 0Eh
0x1800b2ccc  test    rbp, rbp
0x1800b2ccf  jz      short loc_1800B2CD9
0x1800b2cd1  mov     rcx, rbp; lpMem
0x1800b2cd4  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x1800b2cd9  test    r15d, r15d
0x1800b2cdc  mov     eax, edi
0x1800b2cde  mov     ecx, 6E6h
0x1800b2ce3  cmovz   eax, ecx
0x1800b2ce6  add     rsp, 48h
0x1800b2cea  pop     r15
0x1800b2cec  pop     r14
0x1800b2cee  pop     r13
0x1800b2cf0  pop     r12
0x1800b2cf2  pop     rdi
0x1800b2cf3  pop     rsi
0x1800b2cf4  pop     rbp
0x1800b2cf5  pop     rbx
0x1800b2cf6  retn
0x1800b2cf7  call    cs:__imp_GetCommandLineW
0x1800b2cfd  mov     rcx, rax; Str
0x1800b2d00  mov     edx, 5Ch ; '\'; Ch
0x1800b2d05  mov     rbx, rax
0x1800b2d08  call    cs:__imp_wcsrchr
0x1800b2d0e  mov     ecx, r13d
0x1800b2d11  mov     rsi, r13
0x1800b2d14  test    rax, rax
0x1800b2d17  lea     r12, [rax+2]
0x1800b2d1b  cmovz   r12, rbx
0x1800b2d1f  mov     rbx, rbp
0x1800b2d22  cmp     [rbx], r13w
0x1800b2d26  jz      loc_1800B2DE7
0x1800b2d2c  mov     edx, ecx
0x1800b2d2e  test    ecx, ecx
0x1800b2d30  jz      loc_1800B2DCF
0x1800b2d36  sub     edx, 1
0x1800b2d39  jz      short loc_1800B2DB1
0x1800b2d3b  sub     edx, 1
0x1800b2d3e  jz      short loc_1800B2D89
0x1800b2d40  cmp     edx, 1
0x1800b2d43  jnz     short loc_1800B2DA8
0x1800b2d45  cmp     word ptr [rbx], 22h ; '"'
0x1800b2d49  jnz     short loc_1800B2D64
0x1800b2d4b  mov     rdx, rsi; unsigned __int16 *
0x1800b2d4e  mov     [rbx], r13w
0x1800b2d52  mov     rcx, r12; unsigned __int16 *
0x1800b2d55  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b2d5a  test    eax, eax
0x1800b2d5c  jnz     short loc_1800B2D7D
0x1800b2d5e  lea     rsi, [rbx+2]
0x1800b2d62  jmp     short loc_1800B2DA3
0x1800b2d64  cmp     word ptr [rbx], 20h ; ' '
0x1800b2d68  jnz     short loc_1800B2DA8
0x1800b2d6a  mov     rdx, rsi; unsigned __int16 *
0x1800b2d6d  mov     [rbx], r13w
0x1800b2d71  mov     rcx, r12; unsigned __int16 *
0x1800b2d74  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b2d79  test    eax, eax
0x1800b2d7b  jz      short loc_1800B2DA3
0x1800b2d7d  mov     dword ptr [r14], 1
0x1800b2d84  jmp     loc_1800B2CD1
0x1800b2d89  cmp     word ptr [rbx], 22h ; '"'
0x1800b2d8d  jnz     short loc_1800B2D9A
0x1800b2d8f  lea     rsi, [rbx+2]
0x1800b2d93  mov     ecx, 1
0x1800b2d98  jmp     short loc_1800B2DA8
0x1800b2d9a  cmp     word ptr [rbx], 20h ; ' '
0x1800b2d9e  jz      short loc_1800B2DA8
0x1800b2da0  mov     rsi, rbx
0x1800b2da3  mov     ecx, 3
0x1800b2da8  add     rbx, 2
0x1800b2dac  jmp     loc_1800B2D22
0x1800b2db1  cmp     word ptr [rbx], 22h ; '"'
0x1800b2db5  jnz     short loc_1800B2DA8
0x1800b2db7  mov     rdx, rsi; unsigned __int16 *
0x1800b2dba  mov     [rbx], r13w
0x1800b2dbe  mov     rcx, r12; unsigned __int16 *
0x1800b2dc1  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b2dc6  test    eax, eax
0x1800b2dc8  jnz     short loc_1800B2D7D
0x1800b2dca  mov     ecx, r13d
0x1800b2dcd  jmp     short loc_1800B2DA8
0x1800b2dcf  cmp     word ptr [rbx], 22h ; '"'
0x1800b2dd3  jnz     short loc_1800B2DDA
0x1800b2dd5  mov     rsi, rbx
0x1800b2dd8  jmp     short loc_1800B2D93
0x1800b2dda  cmp     word ptr [rbx], 20h ; ' '
0x1800b2dde  jnz     short loc_1800B2DA0
0x1800b2de0  mov     ecx, 2
0x1800b2de5  jmp     short loc_1800B2DA8
0x1800b2de7  test    rsi, rsi
0x1800b2dea  jz      loc_1800B2CD1
0x1800b2df0  mov     rdx, rsi; unsigned __int16 *
0x1800b2df3  mov     rcx, r12; unsigned __int16 *
0x1800b2df6  call    ?DoesThisProcessCmdLineStartWithThisString@@YAHPEAG0@Z; DoesThisProcessCmdLineStartWithThisString(ushort *,ushort *)
0x1800b2dfb  test    eax, eax
0x1800b2dfd  jz      loc_1800B2CD1
0x1800b2e03  jmp     loc_1800B2D7D
0x1800b2e08  mov     eax, 0Eh
0x1800b2e0d  jmp     loc_1800B2CE6
```
