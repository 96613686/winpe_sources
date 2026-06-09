# CWMWriter::ReadFromStream(IStream *)

- ea: `0x180010d60`
- end: `0x180010df3`
- name: `?ReadFromStream@CWMWriter@@UEAAJPEAUIStream@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x180010d60`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriter::ReadFromStream(CWMWriter *this, struct IStream *a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  __int64 result; // rax
  char *v5; // rcx
  __int64 v6; // rax
  _OWORD v7[2]; // [rsp+30h] [rbp-38h] BYREF

  lpVtbl = a2->lpVtbl;
  memset(v7, 0, 28);
  result = ((__int64 (__fastcall *)(struct IStream *, _OWORD *, __int64))lpVtbl->Read)(a2, v7, 28);
  if ( (int)result >= 0 )
  {
    if ( LODWORD(v7[0]) == 28 )
    {
      v5 = (char *)this - 8;
      v6 = *((_QWORD *)this - 1);
      if ( DWORD2(v7[0]) == 1 )
        return (*(__int64 (__fastcall **)(char *, char *))(v6 + 40))(v5, (char *)v7 + 12);
      else
        return (*(__int64 (__fastcall **)(char *, _QWORD))(v6 + 24))(v5, DWORD1(v7[0]));
    }
    else
    {
      return 2147746372LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010d60  push    rbx
0x180010d62  sub     rsp, 60h
0x180010d66  mov     rax, cs:__security_cookie
0x180010d6d  xor     rax, rsp
0x180010d70  mov     [rsp+68h+var_18], rax
0x180010d75  mov     rax, [rdx]
0x180010d78  mov     r10, rdx
0x180010d7b  xorps   xmm0, xmm0
0x180010d7e  lea     rdx, [rsp+68h+var_38]
0x180010d83  xor     r9d, r9d
0x180010d86  mov     rbx, rcx
0x180010d89  movups  [rsp+68h+var_38], xmm0
0x180010d8e  mov     rax, [rax+18h]
0x180010d92  mov     rcx, r10
0x180010d95  movups  [rsp+68h+var_38+0Ch], xmm0
0x180010d9a  lea     r8d, [r9+1Ch]
0x180010d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010da3  test    eax, eax
0x180010da5  js      short loc_180010DE0
0x180010da7  cmp     dword ptr [rsp+68h+var_38], 1Ch
0x180010dac  jz      short loc_180010DB5
0x180010dae  mov     eax, 80040244h
0x180010db3  jmp     short loc_180010DE0
0x180010db5  cmp     dword ptr [rsp+68h+var_38+8], 1
0x180010dba  lea     rcx, [rbx-8]
0x180010dbe  mov     rax, [rcx]
0x180010dc1  jnz     short loc_180010DD3
0x180010dc3  mov     rax, [rax+28h]
0x180010dc7  lea     rdx, [rsp+68h+var_38+0Ch]
0x180010dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dd1  jmp     short loc_180010DE0
0x180010dd3  mov     edx, dword ptr [rsp+68h+var_38+4]
0x180010dd7  mov     rax, [rax+18h]
0x180010ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010de0  mov     rcx, [rsp+68h+var_18]
0x180010de5  xor     rcx, rsp; StackCookie
0x180010de8  call    __security_check_cookie
0x180010ded  add     rsp, 60h
0x180010df1  pop     rbx
0x180010df2  retn
```
