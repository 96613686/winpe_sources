# SipFile::GetFileType(FileType *)

- ea: `0x180003fe4`
- end: `0x180004096`
- name: `?GetFileType@SipFile@@QEAAKPEAW4FileType@@@Z`
- size: `178`
- prototype: `unsigned int __fastcall(SipFile *__hidden this, enum FileType *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180001e40`
- `0x1800025b0`
- `0x1800034d4`
- `0x180003648`

## callees

- `0x180003ab0`
- `0x180003fe4`
- `0x180004ec0`
- `0x1800054f0`

## pseudocode

```c
__int64 __fastcall SipFile::GetFileType(SipFile *this, enum FileType *a2)
{
  unsigned int v4; // ebx
  int v5; // ecx
  unsigned int v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF

  if ( a2 )
  {
    *(_DWORD *)a2 = 0;
    v5 = *((_DWORD *)this + 13);
    if ( (unsigned int)(v5 - 1) <= 3 )
    {
      v4 = 0;
    }
    else
    {
      if ( *((_QWORD *)this + 4) == -1 )
        return 6;
      v7 = 0;
      v4 = SipFile::Read(this, (__int64)a2, 0x20u, v8, &v7);
      if ( v4 )
        return v4;
      v5 = DetermineFileType(v8, v7);
      *((_DWORD *)this + 13) = v5;
    }
    *(_DWORD *)a2 = v5;
    return v4;
  }
  return 87;
}

```

## disassembly

```asm
0x180003fe4  mov     [rsp+arg_10], rbx
0x180003fe9  mov     [rsp+arg_18], rsi
0x180003fee  push    rdi
0x180003fef  sub     rsp, 60h
0x180003ff3  mov     rax, cs:__security_cookie
0x180003ffa  xor     rax, rsp
0x180003ffd  mov     [rsp+68h+var_10], rax
0x180004002  mov     rsi, rdx
0x180004005  mov     rdi, rcx
0x180004008  test    rdx, rdx
0x18000400b  jnz     short loc_180004012
0x18000400d  lea     ebx, [rdx+57h]
0x180004010  jmp     short loc_180004075
0x180004012  mov     dword ptr [rdx], 0
0x180004018  mov     ecx, [rcx+34h]
0x18000401b  lea     eax, [rcx-1]
0x18000401e  cmp     eax, 3
0x180004021  jbe     short loc_180004071
0x180004023  cmp     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x180004028  jnz     short loc_180004031
0x18000402a  mov     ebx, 6
0x18000402f  jmp     short loc_180004075
0x180004031  lea     rax, [rsp+68h+var_38]
0x180004036  mov     [rsp+68h+var_38], 0
0x18000403e  lea     r9, [rsp+68h+var_30]; void *
0x180004043  mov     [rsp+68h+var_48], rax; unsigned int *
0x180004048  mov     r8d, 20h ; ' '; unsigned int
0x18000404e  mov     rcx, rdi; this
0x180004051  call    ?Read@SipFile@@QEAAK_KKPEAXPEAK@Z; SipFile::Read(unsigned __int64,ulong,void *,ulong *)
0x180004056  mov     ebx, eax
0x180004058  test    eax, eax
0x18000405a  jnz     short loc_180004075
0x18000405c  mov     edx, [rsp+68h+var_38]
0x180004060  lea     rcx, [rsp+68h+var_30]
0x180004065  call    ?DetermineFileType@@YA?AW4FileType@@PEBEI@Z; DetermineFileType(uchar const *,uint)
0x18000406a  mov     ecx, eax
0x18000406c  mov     [rdi+34h], eax
0x18000406f  jmp     short loc_180004073
0x180004071  xor     ebx, ebx
0x180004073  mov     [rsi], ecx
0x180004075  mov     eax, ebx
0x180004077  mov     rcx, [rsp+68h+var_10]
0x18000407c  xor     rcx, rsp; StackCookie
0x18000407f  call    __security_check_cookie
0x180004084  lea     r11, [rsp+68h+var_8]
0x180004089  mov     rbx, [r11+20h]
0x18000408d  mov     rsi, [r11+28h]
0x180004091  mov     rsp, r11
0x180004094  pop     rdi
0x180004095  retn
```
