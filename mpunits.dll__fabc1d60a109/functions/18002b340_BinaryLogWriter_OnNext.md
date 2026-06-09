# BinaryLogWriter_OnNext

- ea: `0x18002b340`
- end: `0x18002b481`
- name: `BinaryLogWriter_OnNext`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800074b0`
- `0x1800077a0`
- `0x180007800`
- `0x180008a90`
- `0x18000af38`
- `0x18000b0d8`
- `0x180027f20`
- `0x18002b340`
- `0x180044842`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `msvcrt!_close` at `0x18002b404`
- `msvcrt!_close` at `0x18002b404`

## pseudocode

```c
__int64 (**__fastcall BinaryLogWriter_OnNext(__int64 a1, __int64 a2))(void)
{
  __int64 v4; // rdi
  __int64 (**result)(void); // rax
  unsigned int v6; // esi
  __int64 v7; // rbx
  __int64 (***v8)(void); // [rsp+20h] [rbp-69h] BYREF
  __int64 v9; // [rsp+28h] [rbp-61h] BYREF
  _BYTE v10[128]; // [rsp+30h] [rbp-59h] BYREF

  v8 = 0;
  v9 = 0;
  v4 = a1 + 152;
  result = (__int64 (**)(void))memset_0(v10, 0, 0x78u);
  if ( !*(_BYTE *)(v4 + 120) )
  {
    v6 = Item_ToInstance(a2, v10, &v9);
    if ( v6
      || (v7 = EnableErrorDetails(),
          v6 = BinaryLogWriter_WriteInstance(v9, v4),
          CatchErrorDetails(v7, &v8),
          BoxFree(v10),
          v6) )
    {
      *(_BYTE *)(v4 + 120) = 1;
      if ( *(_DWORD *)v4 != -1 )
      {
        _close(*(_DWORD *)v4);
        *(_DWORD *)v4 = -1;
        trace_BinLogWriter_ClosedLogFile();
      }
      ((void (__fastcall *)(__int64, _QWORD, __int64 (***)(void)))ObserverProtocol_PostErrorAndDispose)(a1, v6, v8);
      result = (__int64 (**)(void))trace_BinLogWriter_Trminated(v6);
    }
    else
    {
      result = (__int64 (**)(void))((__int64 (__fastcall *)(__int64, __int64))ObserverProtocol_PostNext)(a1, a2);
    }
    if ( v8 )
    {
      result = *v8;
      if ( *v8 )
        return (__int64 (**)(void))result[2]();
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b340  mov     [rsp-8+arg_10], rbx
0x18002b345  push    rbp
0x18002b346  push    rsi
0x18002b347  push    rdi
0x18002b348  push    r14
0x18002b34a  push    r15
0x18002b34c  lea     rbp, [rsp-37h]
0x18002b351  sub     rsp, 0C0h
0x18002b358  mov     rax, cs:__security_cookie
0x18002b35f  xor     rax, rsp
0x18002b362  mov     [rbp+57h+var_30], rax
0x18002b366  mov     r15, rdx
0x18002b369  mov     [rbp+57h+var_C0], 0
0x18002b371  xor     edx, edx; Val
0x18002b373  mov     [rbp+57h+var_B8], 0
0x18002b37b  mov     r14, rcx
0x18002b37e  lea     rdi, [rcx+98h]
0x18002b385  lea     rcx, [rbp+57h+var_B0]; void *
0x18002b389  lea     r8d, [rdx+78h]; Size
0x18002b38d  call    memset_0
0x18002b392  cmp     byte ptr [rdi+78h], 0
0x18002b396  jnz     loc_18002B45E
0x18002b39c  lea     r8, [rbp+57h+var_B8]
0x18002b3a0  mov     rcx, r15
0x18002b3a3  lea     rdx, [rbp+57h+var_B0]
0x18002b3a7  call    Item_ToInstance
0x18002b3ac  mov     esi, eax
0x18002b3ae  test    eax, eax
0x18002b3b0  jnz     short loc_18002B3F9
0x18002b3b2  call    EnableErrorDetails
0x18002b3b7  mov     rcx, [rbp+57h+var_B8]
0x18002b3bb  mov     rdx, rdi
0x18002b3be  mov     rbx, rax
0x18002b3c1  call    BinaryLogWriter_WriteInstance
0x18002b3c6  lea     rdx, [rbp+57h+var_C0]
0x18002b3ca  mov     rcx, rbx
0x18002b3cd  mov     esi, eax
0x18002b3cf  call    CatchErrorDetails
0x18002b3d4  lea     rcx, [rbp+57h+var_B0]
0x18002b3d8  call    BoxFree
0x18002b3dd  test    esi, esi
0x18002b3df  jnz     short loc_18002B3F9
0x18002b3e1  mov     rax, cs:off_180047BB0
0x18002b3e8  mov     rdx, r15
0x18002b3eb  mov     rcx, r14
0x18002b3ee  mov     rax, [rax+20h]
0x18002b3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f7  jmp     short loc_18002B444
0x18002b3f9  mov     byte ptr [rdi+78h], 1
0x18002b3fd  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18002b400  jz      short loc_18002B415
0x18002b402  mov     ecx, [rdi]; FileHandle
0x18002b404  call    cs:__imp__close
0x18002b40a  mov     dword ptr [rdi], 0FFFFFFFFh
0x18002b410  call    trace_BinLogWriter_ClosedLogFile
0x18002b415  mov     rax, cs:off_180047BB0
0x18002b41c  mov     edx, esi
0x18002b41e  mov     r8, [rbp+57h+var_C0]
0x18002b422  mov     rcx, r14
0x18002b425  mov     rax, [rax+60h]
0x18002b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b42e  mov     rdx, [rbp+57h+var_C0]
0x18002b432  test    rdx, rdx
0x18002b435  jz      short loc_18002B43D
0x18002b437  mov     edx, [rdx+110h]
0x18002b43d  mov     ecx, esi
0x18002b43f  call    trace_BinLogWriter_Trminated
0x18002b444  mov     rcx, [rbp+57h+var_C0]
0x18002b448  test    rcx, rcx
0x18002b44b  jz      short loc_18002B45E
0x18002b44d  mov     rax, [rcx]
0x18002b450  test    rax, rax
0x18002b453  jz      short loc_18002B45E
0x18002b455  mov     rax, [rax+10h]
0x18002b459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b45e  mov     rcx, [rbp+57h+var_30]
0x18002b462  xor     rcx, rsp; StackCookie
0x18002b465  call    __security_check_cookie
0x18002b46a  mov     rbx, [rsp+0E0h+arg_10]
0x18002b472  add     rsp, 0C0h
0x18002b479  pop     r15
0x18002b47b  pop     r14
0x18002b47d  pop     rdi
0x18002b47e  pop     rsi
0x18002b47f  pop     rbp
0x18002b480  retn
```
