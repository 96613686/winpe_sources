# BluetoothConnection::HrIsConnectedToRemote(int *,uchar * const)

- ea: `0x18002926c`
- end: `0x180029304`
- name: `?HrIsConnectedToRemote@BluetoothConnection@@AEAAJPEAHQEAE@Z`
- size: `152`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, int *, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027c40`
- `0x180028250`

## callees

- `0x180001710`
- `0x18002926c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800292dd`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::HrIsConnectedToRemote(
        BluetoothConnection *this,
        int *a2,
        unsigned __int8 *const a3)
{
  int v5; // edi
  _WORD *v6; // rcx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+28h] [rbp-30h] BYREF

  pv = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(char *, int *, LPVOID *))(*((_QWORD *)this + 4) + 56LL))((char *)this + 32, &v9, &pv);
  if ( v5 >= 0 )
  {
    if ( v9 )
    {
      v6 = pv;
      *a2 = 1;
      if ( a3 )
      {
        *(_DWORD *)a3 = *(_DWORD *)v6;
        *((_WORD *)a3 + 2) = v6[2];
      }
      CoTaskMemFree(v6);
    }
    else
    {
      *a2 = 0;
      return 0;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002926c  push    rbx
0x18002926e  push    rsi
0x18002926f  push    rdi
0x180029270  sub     rsp, 40h
0x180029274  mov     rax, cs:__security_cookie
0x18002927b  xor     rax, rsp
0x18002927e  mov     [rsp+58h+var_28], rax
0x180029283  add     rcx, 20h ; ' '
0x180029287  mov     [rsp+58h+pv], 0
0x180029290  mov     rbx, r8
0x180029293  mov     [rsp+58h+var_30], 0
0x18002929b  mov     rsi, rdx
0x18002929e  lea     r8, [rsp+58h+pv]
0x1800292a3  lea     rdx, [rsp+58h+var_30]
0x1800292a8  mov     rax, [rcx]
0x1800292ab  mov     rax, [rax+38h]
0x1800292af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292b4  mov     edi, eax
0x1800292b6  test    eax, eax
0x1800292b8  js      short loc_1800292ED
0x1800292ba  cmp     [rsp+58h+var_30], 0
0x1800292bf  jz      short loc_1800292E5
0x1800292c1  mov     rcx, [rsp+58h+pv]; pv
0x1800292c6  mov     dword ptr [rsi], 1
0x1800292cc  test    rbx, rbx
0x1800292cf  jz      short loc_1800292DD
0x1800292d1  mov     edx, [rcx]
0x1800292d3  mov     [rbx], edx
0x1800292d5  movzx   eax, word ptr [rcx+4]
0x1800292d9  mov     [rbx+4], ax
0x1800292dd  call    cs:__imp_CoTaskMemFree
0x1800292e3  jmp     short loc_1800292ED
0x1800292e5  mov     dword ptr [rsi], 0
0x1800292eb  xor     edi, edi
0x1800292ed  mov     eax, edi
0x1800292ef  mov     rcx, [rsp+58h+var_28]
0x1800292f4  xor     rcx, rsp; StackCookie
0x1800292f7  call    __security_check_cookie
0x1800292fc  add     rsp, 40h
0x180029300  pop     rdi
0x180029301  pop     rsi
0x180029302  pop     rbx
0x180029303  retn
```
