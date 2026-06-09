# CRegNode::MoveToParentKeyOfKey(void)

- ea: `0x180034df0`
- end: `0x180034f5c`
- name: `?MoveToParentKeyOfKey@CRegNode@@UEAAJXZ`
- size: `364`
- prototype: `__int64 __fastcall(CRegNode *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180034934`
- `0x180034df0`
- `0x180034f88`
- `0x180055880`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180034eb2`
- `msvcrt!wcsrchr` at `0x180034eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ee3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034f1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e64`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegNode::MoveToParentKeyOfKey(CRegNode *this)
{
  HKEY v2; // r12
  unsigned __int16 *v3; // rdi
  __int64 v4; // r13
  int v5; // r15d
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int16 *v8; // r14
  unsigned __int16 *p_Str; // rsi
  unsigned __int16 *v10; // rax
  int v12; // ebp
  __int64 v13; // r10
  wchar_t *v14; // rax
  wchar_t Str; // [rsp+20h] [rbp-828h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 3);
  v3 = (unsigned __int16 *)*((_QWORD *)this + 4);
  v4 = *((_QWORD *)this + 5);
  v5 = *((_DWORD *)this + 20);
  v6 = -1;
  do
    ++v6;
  while ( v3[v6] );
  v7 = 1000;
  if ( v6 >= 0x3E8 )
  {
    v7 = v6 + 1;
    v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v6 + 1, 2u));
    p_Str = v10;
    if ( !v10 )
      return 2147942414LL;
    v8 = v10;
  }
  else
  {
    v8 = 0;
    p_Str = &Str;
  }
  v12 = StringCchCopyW(p_Str, v7, v3);
  if ( v12 >= 0 )
  {
    *((_QWORD *)this + 3) = *((_QWORD *)this + 2);
    *((_QWORD *)this + 4) = v13;
    *((_QWORD *)this + 5) = v13;
    *((_DWORD *)this + 20) = v13;
    v14 = wcsrchr(p_Str, 0x5Cu);
    if ( v14 )
      *v14 = 0;
    v12 = CRegNode::MoveToDescendantOr(this, 0, p_Str, L"\\");
    v13 = 0;
  }
  if ( v8 )
  {
    CoTaskMemFree(p_Str);
    v13 = 0;
  }
  if ( v12 < 0 )
  {
    *((_QWORD *)this + 3) = v2;
    *((_QWORD *)this + 4) = v3;
    *((_QWORD *)this + 5) = v4;
    *((_DWORD *)this + 20) = v5;
    return (unsigned int)v12;
  }
  if ( *((_QWORD *)this + 9) == v13 )
  {
    RegSafeCloseKey(v2);
    if ( !v3 )
      return (unsigned int)v12;
  }
  else if ( !v5 || !v3 )
  {
    return (unsigned int)v12;
  }
  CoTaskMemFree(v3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180034df0  push    rbx
0x180034df2  push    rbp
0x180034df3  push    rsi
0x180034df4  push    rdi
0x180034df5  push    r12
0x180034df7  push    r13
0x180034df9  push    r14
0x180034dfb  push    r15
0x180034dfd  sub     rsp, 808h
0x180034e04  mov     rax, cs:__security_cookie
0x180034e0b  xor     rax, rsp
0x180034e0e  mov     [rsp+848h+var_58], rax
0x180034e16  mov     rbx, rcx
0x180034e19  mov     r12, [rcx+18h]
0x180034e1d  mov     rdi, [rcx+20h]
0x180034e21  mov     r13, [rcx+28h]
0x180034e25  mov     r15d, [rcx+50h]
0x180034e29  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180034e2d  mov     rax, rcx
0x180034e30  xor     r10d, r10d
0x180034e33  inc     rax
0x180034e36  cmp     [rdi+rax*2], r10w
0x180034e3b  jnz     short loc_180034E33
0x180034e3d  mov     ebp, 3E8h
0x180034e42  cmp     rax, rbp
0x180034e45  jnb     short loc_180034E51
0x180034e47  mov     r14, r10
0x180034e4a  lea     rsi, [rsp+848h+Str]
0x180034e4f  jmp     short loc_180034E82
0x180034e51  lea     rbp, [rax+1]
0x180034e55  mov     eax, 2
0x180034e5a  mul     rbp
0x180034e5d  cmovb   rax, rcx
0x180034e61  mov     rcx, rax; cb
0x180034e64  call    cs:__imp_CoTaskMemAlloc
0x180034e6a  mov     rsi, rax
0x180034e6d  xor     r10d, r10d
0x180034e70  test    rax, rax
0x180034e73  jnz     short loc_180034E7F
0x180034e75  mov     eax, 8007000Eh
0x180034e7a  jmp     loc_180034F38
0x180034e7f  mov     r14, rax
0x180034e82  mov     r8, rdi; unsigned __int16 *
0x180034e85  mov     rdx, rbp; unsigned __int64
0x180034e88  mov     rcx, rsi; unsigned __int16 *
0x180034e8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034e90  mov     ebp, eax
0x180034e92  test    eax, eax
0x180034e94  js      short loc_180034EDB
0x180034e96  mov     rax, [rbx+10h]
0x180034e9a  mov     [rbx+18h], rax
0x180034e9e  mov     [rbx+20h], r10
0x180034ea2  mov     [rbx+28h], r10
0x180034ea6  mov     [rbx+50h], r10d
0x180034eaa  mov     edx, 5Ch ; '\'; Ch
0x180034eaf  mov     rcx, rsi; Str
0x180034eb2  call    cs:__imp_wcsrchr
0x180034eb8  test    rax, rax
0x180034ebb  jz      short loc_180034EC2
0x180034ebd  xor     ecx, ecx
0x180034ebf  mov     [rax], cx
0x180034ec2  lea     r9, asc_180061B34; "\\"
0x180034ec9  mov     r8, rsi; unsigned __int16 *
0x180034ecc  xor     edx, edx; unsigned int
0x180034ece  mov     rcx, rbx; this
0x180034ed1  call    ?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z; CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)
0x180034ed6  mov     ebp, eax
0x180034ed8  xor     r10d, r10d
0x180034edb  test    r14, r14
0x180034ede  jz      short loc_180034EED
0x180034ee0  mov     rcx, rsi; pv
0x180034ee3  call    cs:__imp_CoTaskMemFree
0x180034ee9  nop
0x180034eea  xor     r10d, r10d
0x180034eed  test    ebp, ebp
0x180034eef  js      short loc_180034F26
0x180034ef1  cmp     [rbx+48h], r10
0x180034ef5  jz      short loc_180034F0D
0x180034ef7  test    r15d, r15d
0x180034efa  jz      short loc_180034F36
0x180034efc  test    rdi, rdi
0x180034eff  jz      short loc_180034F36
0x180034f01  mov     rcx, rdi; pv
0x180034f04  call    cs:__imp_CoTaskMemFree
0x180034f0a  nop
0x180034f0b  jmp     short loc_180034F36
0x180034f0d  mov     rcx, r12; HKEY
0x180034f10  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180034f15  test    rdi, rdi
0x180034f18  jz      short loc_180034F36
0x180034f1a  mov     rcx, rdi; pv
0x180034f1d  call    cs:__imp_CoTaskMemFree
0x180034f23  nop
0x180034f24  jmp     short loc_180034F36
0x180034f26  mov     [rbx+18h], r12
0x180034f2a  mov     [rbx+20h], rdi
0x180034f2e  mov     [rbx+28h], r13
0x180034f32  mov     [rbx+50h], r15d
0x180034f36  mov     eax, ebp
0x180034f38  mov     rcx, [rsp+848h+var_58]
0x180034f40  xor     rcx, rsp; StackCookie
0x180034f43  call    __security_check_cookie
0x180034f48  add     rsp, 808h
0x180034f4f  pop     r15
0x180034f51  pop     r14
0x180034f53  pop     r13
0x180034f55  pop     r12
0x180034f57  pop     rdi
0x180034f58  pop     rsi
0x180034f59  pop     rbp
0x180034f5a  pop     rbx
0x180034f5b  retn
```
