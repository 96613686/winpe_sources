# GetLineAndCallObjWithReadLock

- ea: `0x18000338c`
- end: `0x180003480`
- name: `GetLineAndCallObjWithReadLock`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003ba8`

## callees

- `0x180001ca4`
- `0x180001f48`
- `0x180002494`
- `0x18000338c`
- `0x1800037a8`
- `0x180007df8`

## string_xrefs

- `0x1800033f2`: `GetLineAndCallObjWithReadLock: inbound ht_call(%p) closed already`
- `0x180003456`: `GetLineAndCallObjWithReadLock: bad call handle(%p, %x)`

## pseudocode

```c
__int64 __fastcall GetLineAndCallObjWithReadLock(const void *a1, const void *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 result; // rax
  __int64 v9; // rbx
  _DWORD *v10; // rbx
  _QWORD *v11; // rcx
  unsigned int Lock; // edi
  unsigned int ObjWithReadLock; // eax
  __int64 v14; // [rsp+20h] [rbp-38h] BYREF
  _DWORD *v15; // [rsp+28h] [rbp-30h] BYREF

  v15 = 0;
  v14 = 0;
  result = GetLineObjWithReadLock(a1, &v14);
  if ( !(_DWORD)result )
  {
    v9 = v14;
    *a3 = v14;
    if ( ((unsigned __int8)a2 & 1) != 0 )
    {
      v10 = *(_DWORD **)(v9 + 24);
      if ( v10 )
      {
        v11 = v10;
        while ( (const void *)v11[7] != a2 )
        {
          v10 = (_DWORD *)v11[6];
          v11 = v10;
          if ( !v10 )
            goto LABEL_7;
        }
        if ( *v10 == 1229144396 )
        {
          Lock = AcquireObjReadLock(v11[2]);
          if ( !Lock )
          {
LABEL_10:
            *a4 = v10;
            return 0;
          }
LABEL_17:
          ReleaseObjReadLock(a1);
          return Lock;
        }
      }
LABEL_7:
      TspLog(2, "GetLineAndCallObjWithReadLock: inbound ht_call(%p) closed already", a2);
    }
    else
    {
      ObjWithReadLock = GetObjWithReadLock(a2, &v15);
      if ( ObjWithReadLock )
      {
        Lock = ObjWithReadLock;
        goto LABEL_17;
      }
      v10 = v15;
      if ( *v15 == 1329807692 )
        goto LABEL_10;
      TspLog(2, "GetLineAndCallObjWithReadLock: bad call handle(%p, %x)", a2, *v15);
      ReleaseObjReadLock(a2);
    }
    Lock = -2147483624;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x18000338c  push    rbx
0x18000338e  push    rbp
0x18000338f  push    rsi
0x180003390  push    rdi
0x180003391  push    r14
0x180003393  sub     rsp, 30h
0x180003397  mov     rdi, rdx
0x18000339a  mov     [rsp+58h+var_30], 0
0x1800033a3  lea     rdx, [rsp+58h+var_38]
0x1800033a8  mov     [rsp+58h+var_38], 0
0x1800033b1  mov     r14, r9
0x1800033b4  mov     rsi, r8
0x1800033b7  mov     rbp, rcx
0x1800033ba  call    GetLineObjWithReadLock
0x1800033bf  test    eax, eax
0x1800033c1  jnz     short loc_180003421
0x1800033c3  mov     rbx, [rsp+58h+var_38]
0x1800033c8  mov     [rsi], rbx
0x1800033cb  test    dil, 1
0x1800033cf  jz      short loc_18000342D
0x1800033d1  mov     rbx, [rbx+18h]
0x1800033d5  test    rbx, rbx
0x1800033d8  jz      short loc_1800033EF
0x1800033da  mov     rcx, rbx
0x1800033dd  cmp     [rcx+38h], rdi
0x1800033e1  jz      short loc_180003405
0x1800033e3  mov     rbx, [rcx+30h]
0x1800033e7  mov     rcx, rbx
0x1800033ea  test    rbx, rbx
0x1800033ed  jnz     short loc_1800033DD
0x1800033ef  mov     r8, rdi
0x1800033f2  lea     rdx, aGetlineandcall_0; "GetLineAndCallObjWithReadLock: inbound "...
0x1800033f9  mov     ecx, 2
0x1800033fe  call    TspLog
0x180003403  jmp     short loc_18000346F
0x180003405  cmp     dword ptr [rbx], 4943414Ch
0x18000340b  jnz     short loc_1800033EF
0x18000340d  mov     rcx, [rcx+10h]
0x180003411  call    AcquireObjReadLock
0x180003416  mov     edi, eax
0x180003418  test    eax, eax
0x18000341a  jnz     short loc_180003474
0x18000341c  mov     [r14], rbx
0x18000341f  xor     eax, eax
0x180003421  add     rsp, 30h
0x180003425  pop     r14
0x180003427  pop     rdi
0x180003428  pop     rsi
0x180003429  pop     rbp
0x18000342a  pop     rbx
0x18000342b  retn
0x18000342d  lea     rdx, [rsp+58h+var_30]
0x180003432  mov     rcx, rdi
0x180003435  call    GetObjWithReadLock
0x18000343a  test    eax, eax
0x18000343c  jz      short loc_180003442
0x18000343e  mov     edi, eax
0x180003440  jmp     short loc_180003474
0x180003442  mov     rbx, [rsp+58h+var_30]
0x180003447  mov     r9d, [rbx]
0x18000344a  cmp     r9d, 4F43414Ch
0x180003451  jz      short loc_18000341C
0x180003453  mov     r8, rdi
0x180003456  lea     rdx, aGetlineandcall; "GetLineAndCallObjWithReadLock: bad call"...
0x18000345d  mov     ecx, 2
0x180003462  call    TspLog
0x180003467  mov     rcx, rdi
0x18000346a  call    ReleaseObjReadLock
0x18000346f  mov     edi, 80000018h
0x180003474  mov     rcx, rbp
0x180003477  call    ReleaseObjReadLock
0x18000347c  mov     eax, edi
0x18000347e  jmp     short loc_180003421
```
