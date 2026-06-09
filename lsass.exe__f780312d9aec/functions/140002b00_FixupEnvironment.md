# FixupEnvironment

- ea: `0x140002b00`
- end: `0x140002b94`
- name: `FixupEnvironment`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031bc`

## callees

- `0x1400020c0`
- `0x140002b00`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140002b40`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x140002b40`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140002b6d`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140002b6d`

## string_xrefs

- `0x140002b21`: `\System32`

## pseudocode

```c
DWORD FixupEnvironment()
{
  DWORD result; // eax
  WCHAR Buffer[8]; // [rsp+20h] [rbp-238h] BYREF
  _DWORD v2[128]; // [rsp+30h] [rbp-228h]

  result = GetEnvironmentVariableW(L"SystemRoot", Buffer, 0x104u);
  if ( result )
  {
    if ( 261 - result >= 0xA )
    {
      *(_OWORD *)&Buffer[result] = *(_OWORD *)L"\\System32";
      *(_DWORD *)((char *)v2 + 2 * result) = *(_DWORD *)L"2";
      return SetEnvironmentVariableW(L"Path", Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002b00  mov     rax, rsp
0x140002b03  push    rbx
0x140002b04  sub     rsp, 250h
0x140002b0b  movaps  xmmword ptr [rax-18h], xmm6
0x140002b0f  mov     rax, cs:__security_cookie
0x140002b16  xor     rax, rsp
0x140002b19  mov     [rsp+258h+var_28], rax
0x140002b21  movups  xmm6, xmmword ptr cs:aSystem32; "\\System32"
0x140002b28  mov     ebx, dword ptr cs:aSystem32+10h; "2"
0x140002b2e  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x140002b33  mov     r8d, 104h; nSize
0x140002b39  lea     rcx, Name; "SystemRoot"
0x140002b40  call    cs:__imp_GetEnvironmentVariableW
0x140002b46  test    eax, eax
0x140002b48  jz      short loc_140002B73
0x140002b4a  mov     ecx, 105h
0x140002b4f  sub     ecx, eax
0x140002b51  cmp     ecx, 0Ah
0x140002b54  jb      short loc_140002B73
0x140002b56  mov     eax, eax
0x140002b58  lea     rdx, [rsp+258h+Buffer]; lpValue
0x140002b5d  lea     rcx, aPath; "Path"
0x140002b64  movups  xmmword ptr [rsp+rax*2+258h+Buffer], xmm6
0x140002b69  mov     [rsp+rax*2+258h+var_228], ebx
0x140002b6d  call    cs:__imp_SetEnvironmentVariableW
0x140002b73  mov     rcx, [rsp+258h+var_28]
0x140002b7b  xor     rcx, rsp; StackCookie
0x140002b7e  call    __security_check_cookie
0x140002b83  movaps  xmm6, [rsp+258h+var_18]
0x140002b8b  add     rsp, 250h
0x140002b92  pop     rbx
0x140002b93  retn
```
