# CFveApiBase::GetLoggingServiceName(void)

- ea: `0x180055c44`
- end: `0x180055d03`
- name: `?GetLoggingServiceName@CFveApiBase@@QEAAPEBGXZ`
- size: `191`
- prototype: `const unsigned __int16 *__fastcall(CFveApiBase *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180053e94`
- `0x180054f2c`
- `0x1800b1450`
- `0x1800b6964`
- `0x1800c5324`

## callees

- `0x180042998`
- `0x180055c44`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180055c79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180055c79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ce0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ce0`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180055ca2`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180055ca2`

## pseudocode

```c
unsigned __int16 *__fastcall CFveApiBase::GetLoggingServiceName(CFveApiBase *this)
{
  unsigned __int16 *v1; // rbx
  _DWORD v3[6]; // [rsp+20h] [rbp-28h] BYREF

  v1 = (unsigned __int16 *)((char *)this + 406);
  memset(&v3[1], 0, 20);
  *((_WORD *)this + 203) = 0;
  v3[0] = GetCurrentProcessId();
  v3[1] = NtCurrentTeb()->SubProcessTag;
  if ( !(unsigned int)I_QueryTagInformation(0, 1, v3) )
  {
    if ( !*(_QWORD *)&v3[4] )
      return v1;
    if ( (int)StringCchCopyNW(v1, 0x101u, *(const unsigned __int16 **)&v3[4], 0x100u) < 0 )
      *v1 = 0;
  }
  if ( *(_QWORD *)&v3[4] )
    LocalFree(*(HLOCAL *)&v3[4]);
  return v1;
}

```

## disassembly

```asm
0x180055c44  push    rbx
0x180055c46  sub     rsp, 40h
0x180055c4a  mov     rax, cs:__security_cookie
0x180055c51  xor     rax, rsp
0x180055c54  mov     [rsp+48h+var_10], rax
0x180055c59  xor     eax, eax
0x180055c5b  mov     [rsp+48h+var_28], 0
0x180055c63  xorps   xmm0, xmm0
0x180055c66  mov     [rsp+48h+var_14], eax
0x180055c6a  lea     rbx, [rcx+196h]
0x180055c71  movups  xmmword ptr [rsp+48h+hMem], xmm0
0x180055c76  mov     [rbx], ax
0x180055c79  call    cs:__imp_GetCurrentProcessId
0x180055c80  nop     dword ptr [rax+rax+00h]
0x180055c85  mov     [rsp+48h+var_28], eax
0x180055c89  lea     r8, [rsp+48h+var_28]
0x180055c8e  mov     rax, gs:1720h
0x180055c97  mov     edx, 1
0x180055c9c  xor     ecx, ecx
0x180055c9e  mov     dword ptr [rsp+48h+hMem], eax
0x180055ca2  call    cs:__imp_I_QueryTagInformation
0x180055ca9  nop     dword ptr [rax+rax+00h]
0x180055cae  test    eax, eax
0x180055cb0  jnz     short loc_180055CD6
0x180055cb2  mov     r8, [rsp+48h+hMem+0Ch]; unsigned __int16 *
0x180055cb7  test    r8, r8
0x180055cba  jz      short loc_180055CEC
0x180055cbc  mov     edx, 101h; unsigned __int64
0x180055cc1  mov     rcx, rbx; unsigned __int16 *
0x180055cc4  lea     r9d, [rdx-1]; unsigned __int64
0x180055cc8  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180055ccd  test    eax, eax
0x180055ccf  jns     short loc_180055CD6
0x180055cd1  xor     ecx, ecx
0x180055cd3  mov     [rbx], cx
0x180055cd6  mov     rcx, [rsp+48h+hMem+0Ch]; hMem
0x180055cdb  test    rcx, rcx
0x180055cde  jz      short loc_180055CEC
0x180055ce0  call    cs:__imp_LocalFree
0x180055ce7  nop     dword ptr [rax+rax+00h]
0x180055cec  mov     rax, rbx
0x180055cef  mov     rcx, [rsp+48h+var_10]
0x180055cf4  xor     rcx, rsp; StackCookie
0x180055cf7  call    __security_check_cookie
0x180055cfc  add     rsp, 40h
0x180055d00  pop     rbx
0x180055d01  retn
```
