# pSpUtilsQueryOverrideValue

- ea: `0x180020228`
- end: `0x1800202ca`
- name: `pSpUtilsQueryOverrideValue`
- size: `162`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, HANDLE@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180020384`

## callees

- `0x180020228`
- `0x180020fd8`

## string_xrefs

- `0x18002026a`: `LogPath`
- `0x180020293`: `LogPath`

## pseudocode

```c
__int64 __fastcall pSpUtilsQueryOverrideValue(HANDLE KeyHandle, HANDLE a2, __int64 a3, __int64 a4, __int64 a5, int *a6)
{
  __int64 result; // rax
  int v8; // esi

  if ( !KeyHandle )
    return 87;
  v8 = *a6;
  if ( a2 )
    pSetupQueryValue(a2, L"LogPath", (__int64)a6);
  *a6 = v8;
  result = pSetupQueryValue(KeyHandle, L"LogPath", (__int64)a6);
  if ( !(_DWORD)result )
    return 1629;
  return result;
}

```

## disassembly

```asm
0x180020228  mov     [rsp+arg_0], rbx
0x18002022d  mov     [rsp+arg_8], rsi
0x180020232  mov     [rsp+arg_18], r9d
0x180020237  push    rdi
0x180020238  sub     rsp, 30h
0x18002023c  mov     [rsp+38h+arg_18], 0
0x180020244  mov     rax, rdx
0x180020247  mov     rdi, rcx
0x18002024a  test    rcx, rcx
0x18002024d  jnz     short loc_180020254
0x18002024f  lea     eax, [rcx+57h]
0x180020252  jmp     short loc_1800202BA
0x180020254  mov     rbx, [rsp+38h+arg_28]
0x180020259  mov     esi, [rbx]
0x18002025b  test    rax, rax
0x18002025e  jz      short loc_180020289
0x180020260  mov     r9, [rsp+38h+arg_20]
0x180020265  lea     r8, [rsp+38h+arg_18]
0x18002026a  lea     rdx, aLogpath; "LogPath"
0x180020271  mov     [rsp+38h+var_18], rbx; __int64
0x180020276  mov     rcx, rax; KeyHandle
0x180020279  call    pSetupQueryValue
0x18002027e  test    eax, eax
0x180020280  jnz     short loc_180020289
0x180020282  cmp     [rsp+38h+arg_18], 1
0x180020287  jz      short loc_1800202BA
0x180020289  mov     r9, [rsp+38h+arg_20]
0x18002028e  lea     r8, [rsp+38h+arg_18]
0x180020293  lea     rdx, aLogpath; "LogPath"
0x18002029a  mov     [rbx], esi
0x18002029c  mov     rcx, rdi; KeyHandle
0x18002029f  mov     [rsp+38h+var_18], rbx; __int64
0x1800202a4  call    pSetupQueryValue
0x1800202a9  test    eax, eax
0x1800202ab  jnz     short loc_1800202BA
0x1800202ad  cmp     [rsp+38h+arg_18], 1
0x1800202b2  mov     ecx, 65Dh
0x1800202b7  cmovnz  eax, ecx
0x1800202ba  mov     rbx, [rsp+38h+arg_0]
0x1800202bf  mov     rsi, [rsp+38h+arg_8]
0x1800202c4  add     rsp, 30h
0x1800202c8  pop     rdi
0x1800202c9  retn
```
