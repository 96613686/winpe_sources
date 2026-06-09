# LogMessage_HR(ushort,ulong,long,ulong,...)

- ea: `0x18001c8f0`
- end: `0x18001c9e9`
- name: `?LogMessage_HR@@YAXGKJKZZ`
- size: `249`
- prototype: `void(unsigned __int16, unsigned int, int, unsigned int, ...)`
- caller_count: `12`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800021d8`
- `0x180009e8c`
- `0x180010a08`
- `0x180011a30`
- `0x1800140c0`
- `0x180016dc8`
- `0x18001a838`
- `0x18001af70`
- `0x18001cdfc`
- `0x18001f7f0`
- `0x180029b50`
- `0x18002efc8`

## callees

- `0x180006194`
- `0x18001c8f0`
- `0x18003eeb8`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c97e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c97e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c9cb`

## pseudocode

```c
void LogMessage_HR(unsigned __int16 a1, DWORD a2, unsigned int a3, unsigned int a4, ...)
{
  va_list v5; // rsi
  unsigned int v6; // edi
  _QWORD *v7; // rbx
  unsigned int v8; // r9d
  __int64 v9; // r8
  unsigned __int16 v10[8]; // [rsp+28h] [rbp-50h] BYREF
  __int16 v11; // [rsp+38h] [rbp-40h]
  va_list va; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a3 != -2147024882 )
  {
    v11 = 0;
    *(_OWORD *)v10 = 0;
    StringCchPrintfW(v10, 9u, L"%x", a3);
    va_copy(v5, va);
    v6 = a4 + 1;
    if ( a4 + 1 >= a4 )
    {
      v7 = CoTaskMemAlloc(saturated_mul(v6, 8u));
      if ( v7 )
      {
        v8 = 1;
        for ( *v7 = v10; v8 < v6; v7[v9] = *((_QWORD *)v5 - 1) )
        {
          v9 = v8;
          v5 += 8;
          ++v8;
        }
        LogEventMessage(a2);
        CoTaskMemFree(v7);
      }
    }
  }
}

```

## disassembly

```asm
0x18001c8f0  cmp     r8d, 8007000Eh
0x18001c8f7  jz      locret_18001C9E8
0x18001c8fd  mov     [rsp+arg_18], r9d
0x18001c902  push    rbx
0x18001c903  push    rbp
0x18001c904  push    rsi
0x18001c905  push    rdi
0x18001c906  push    r14
0x18001c908  sub     rsp, 50h
0x18001c90c  mov     rax, cs:__security_cookie
0x18001c913  xor     rax, rsp
0x18001c916  mov     [rsp+78h+var_38], rax
0x18001c91b  xor     eax, eax
0x18001c91d  mov     r14d, edx
0x18001c920  movzx   ebp, cx
0x18001c923  mov     [rsp+78h+var_40], ax
0x18001c928  xorps   xmm0, xmm0
0x18001c92b  lea     rcx, [rsp+78h+var_50]; unsigned __int16 *
0x18001c930  mov     r9d, r8d
0x18001c933  lea     r8, asc_1800547C4; "%x"
0x18001c93a  lea     edx, [rax+9]; unsigned __int64
0x18001c93d  movups  xmmword ptr [rsp+78h+var_50], xmm0
0x18001c942  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001c947  mov     eax, [rsp+78h+arg_18]
0x18001c94e  lea     rsi, [rsp+78h+arg_20]
0x18001c956  mov     [rsp+78h+var_58], 0
0x18001c95f  lea     edi, [rax+1]
0x18001c962  cmp     edi, eax
0x18001c964  jb      short loc_18001C9D1
0x18001c966  mov     ecx, edi
0x18001c968  mov     eax, 8
0x18001c96d  mul     rcx
0x18001c970  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c977  cmovb   rax, rcx
0x18001c97b  mov     rcx, rax; cb
0x18001c97e  call    cs:__imp_CoTaskMemAlloc
0x18001c984  mov     rbx, rax
0x18001c987  test    rax, rax
0x18001c98a  jz      short loc_18001C9D1
0x18001c98c  mov     r9d, 1
0x18001c992  lea     rax, [rsp+78h+var_50]
0x18001c997  mov     [rbx], rax
0x18001c99a  cmp     edi, r9d
0x18001c99d  jbe     short loc_18001C9B6
0x18001c99f  mov     r8d, r9d
0x18001c9a2  lea     rsi, [rsi+8]
0x18001c9a6  mov     rax, [rsi-8]
0x18001c9aa  inc     r9d
0x18001c9ad  mov     [rbx+r8*8], rax
0x18001c9b1  cmp     r9d, edi
0x18001c9b4  jb      short loc_18001C99F
0x18001c9b6  movzx   r9d, di
0x18001c9ba  mov     r8, rbx
0x18001c9bd  movzx   edx, bp
0x18001c9c0  mov     ecx, r14d; dwEventID
0x18001c9c3  call    LogEventMessage
0x18001c9c8  mov     rcx, rbx; pv
0x18001c9cb  call    cs:__imp_CoTaskMemFree
0x18001c9d1  mov     rcx, [rsp+78h+var_38]
0x18001c9d6  xor     rcx, rsp; StackCookie
0x18001c9d9  call    __security_check_cookie
0x18001c9de  add     rsp, 50h
0x18001c9e2  pop     r14
0x18001c9e4  pop     rdi
0x18001c9e5  pop     rsi
0x18001c9e6  pop     rbp
0x18001c9e7  pop     rbx
0x18001c9e8  retn
```
