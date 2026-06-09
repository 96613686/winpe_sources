# RegScan::IsRegisteredFileName(ushort *)

- ea: `0x180050adc`
- end: `0x180050b65`
- name: `?IsRegisteredFileName@RegScan@@AEAAHPEAG@Z`
- size: `137`
- prototype: `int(RegScan *__hidden this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050154`
- `0x180050754`
- `0x180050ea0`

## callees

- `0x180050a34`
- `0x180050adc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180050af7`
- `msvcrt!_wcsicmp` at `0x180050b3f`
- `msvcrt!_wcsicmp` at `0x180050af7`
- `msvcrt!_wcsicmp` at `0x180050b3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegScan::IsRegisteredFileName(RegScan *this, unsigned __int16 *a2)
{
  RegScan *v4; // rcx
  BOOL v6; // ebx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  if ( !_wcsicmp(a2, *(const wchar_t **)(*((_QWORD *)this + 12) + 104LL)) )
    return 1;
  pv = 0;
  if ( RegScan::GetLongFileName(v4, a2, (unsigned __int16 **)&pv) )
  {
    CoTaskMemFree(pv);
    return 0;
  }
  else
  {
    v6 = _wcsicmp((const wchar_t *)pv, *(const wchar_t **)(*((_QWORD *)this + 12) + 104LL)) == 0;
    CoTaskMemFree(pv);
    return v6;
  }
}

```

## disassembly

```asm
0x180050adc  mov     [rsp+arg_8], rbx
0x180050ae1  push    rdi
0x180050ae2  sub     rsp, 20h
0x180050ae6  mov     rbx, rdx
0x180050ae9  mov     rdi, rcx
0x180050aec  mov     rdx, [rcx+60h]
0x180050af0  mov     rdx, [rdx+68h]; String2
0x180050af4  mov     rcx, rbx; String1
0x180050af7  call    cs:__imp__wcsicmp
0x180050afd  test    eax, eax
0x180050aff  jnz     short loc_180050B08
0x180050b01  mov     eax, 1
0x180050b06  jmp     short loc_180050B5A
0x180050b08  mov     [rsp+28h+pv], 0
0x180050b11  lea     r8, [rsp+28h+pv]; unsigned __int16 **
0x180050b16  mov     rdx, rbx; unsigned __int16 *
0x180050b19  call    ?GetLongFileName@RegScan@@AEAAJPEAGPEAPEAG@Z; RegScan::GetLongFileName(ushort *,ushort * *)
0x180050b1e  test    eax, eax
0x180050b20  jz      short loc_180050B32
0x180050b22  mov     rcx, [rsp+28h+pv]; pv
0x180050b27  call    cs:__imp_CoTaskMemFree
0x180050b2d  nop
0x180050b2e  xor     eax, eax
0x180050b30  jmp     short loc_180050B5A
0x180050b32  mov     rdx, [rdi+60h]
0x180050b36  mov     rdx, [rdx+68h]; String2
0x180050b3a  mov     rcx, [rsp+28h+pv]; String1
0x180050b3f  call    cs:__imp__wcsicmp
0x180050b45  xor     ebx, ebx
0x180050b47  test    eax, eax
0x180050b49  setz    bl
0x180050b4c  mov     rcx, [rsp+28h+pv]; pv
0x180050b51  call    cs:__imp_CoTaskMemFree
0x180050b57  nop
0x180050b58  mov     eax, ebx
0x180050b5a  mov     rbx, [rsp+28h+arg_8]
0x180050b5f  add     rsp, 20h
0x180050b63  pop     rdi
0x180050b64  retn
```
