# MakePathCanonicalizationProof(ushort const *,STRU *)

- ea: `0x180001f50`
- end: `0x180002192`
- name: `?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z`
- size: `578`
- prototype: `signed int __fastcall(const unsigned __int16 *Src, void **this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002b720`

## callees

- `0x180001b60`
- `0x180001f50`
- `0x180002470`
- `0x18002c476`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800020e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002132`

## pseudocode

```c
signed int __fastcall MakePathCanonicalizationProof(const unsigned __int16 *Src, void **this)
{
  const unsigned __int16 *v3; // rbx
  unsigned int *v4; // rsi
  _WORD *v5; // rcx
  signed int result; // eax
  bool v7; // sf
  __int64 v8; // rbp
  __int64 v9; // rax
  bool v10; // zf
  unsigned int v11; // r14d
  _WORD *v12; // rcx
  __int64 v13; // rdx
  signed int v14; // ecx
  unsigned __int16 v15; // ax
  __int64 v16; // rax
  __int64 v17; // rsi
  _WORD *v18; // rcx
  __int64 v19; // rsi
  signed int LastError; // eax
  unsigned __int64 v21; // rdx
  signed int v22; // eax

  v3 = Src;
  if ( *(_DWORD *)Src == 6029404 )
  {
    v15 = Src[2];
    if ( (v15 == 63 || v15 == 46) && Src[3] == 92 )
    {
      v16 = -1;
      do
        v10 = Src[++v16] == 0;
      while ( !v10 );
      v17 = (unsigned int)(2 * v16);
      if ( *((unsigned int *)this + 10) >= (unsigned __int64)(v17 + 2) )
        goto LABEL_19;
      if ( (unsigned __int64)(v17 + 128) > 0xFFFFFFFF )
        return -2147024362;
      if ( BUFFER::Resize((BUFFER *)this, v17 + 128) )
      {
LABEL_19:
        memcpy_0(this[4], v3, (unsigned int)v17);
        v18 = this[4];
        v19 = (unsigned int)v17 >> 1;
        *((_DWORD *)this + 12) = v19;
        v18[v19] = 0;
        v14 = 0;
      }
      else
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError > 0 )
          v14 = (unsigned __int16)LastError | 0x80070000;
        if ( v14 < 0 )
          return v14;
      }
      *((_WORD *)this[4] + 2) = 63;
      return v14;
    }
    result = STRU::Copy((STRU *)this, L"\\\\?\\UNC\\");
    if ( result < 0 )
      return result;
    v4 = (unsigned int *)(this + 5);
    v3 += 2;
LABEL_8:
    v8 = (unsigned int)(2 * *((_DWORD *)this + 12));
    v9 = -1;
    do
      v10 = v3[++v9] == 0;
    while ( !v10 );
    v11 = 2 * v9;
    if ( *v4 < (unsigned __int64)(unsigned int)(2 * v9) + v8 + 2 )
    {
      v21 = v11 + v8 + 128;
      if ( v21 > 0xFFFFFFFF )
        return -2147024362;
      if ( !BUFFER::Resize((BUFFER *)this, v21) )
      {
        v22 = GetLastError();
        v14 = v22;
        if ( v22 > 0 )
          return (unsigned __int16)v22 | 0x80070000;
        return v14;
      }
    }
    memcpy_0((char *)this[4] + (unsigned int)v8, v3, v11);
    v12 = this[4];
    v13 = (v11 + (unsigned int)v8) >> 1;
    *((_DWORD *)this + 12) = v13;
    v12[v13] = 0;
    return 0;
  }
  v4 = (unsigned int *)(this + 5);
  if ( *((_DWORD *)this + 10) >= 0xAu || BUFFER::Resize((BUFFER *)this, 0x88u) )
  {
    *(_QWORD *)this[4] = 0x5C003F005C005CLL;
    v5 = this[4];
    *((_DWORD *)this + 12) = 4;
    v5[4] = 0;
    goto LABEL_8;
  }
  result = GetLastError();
  v7 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v7 = result < 0;
  }
  if ( !v7 )
    goto LABEL_8;
  return result;
}

```

## disassembly

```asm
0x180001f50  mov     [rsp+arg_10], rbx
0x180001f55  mov     [rsp+arg_18], rbp
0x180001f5a  push    rsi
0x180001f5b  push    rdi
0x180001f5c  push    r14
0x180001f5e  sub     rsp, 20h
0x180001f62  cmp     word ptr [rcx], 5Ch ; '\'
0x180001f66  mov     rdi, rdx
0x180001f69  mov     rbx, rcx
0x180001f6c  jz      loc_18000204E
0x180001f72  cmp     dword ptr [rdx+28h], 0Ah
0x180001f76  lea     rsi, [rdx+28h]
0x180001f7a  jb      short loc_180001FA0
0x180001f7c  mov     rax, [rdi+20h]
0x180001f80  mov     rcx, 5C003F005C005Ch
0x180001f8a  mov     [rax], rcx
0x180001f8d  xor     eax, eax
0x180001f8f  mov     rcx, [rdi+20h]
0x180001f93  mov     dword ptr [rdi+30h], 4
0x180001f9a  mov     [rcx+8], ax
0x180001f9e  jmp     short loc_180001FC7
0x180001fa0  mov     edx, 88h; unsigned int
0x180001fa5  mov     rcx, rdi; this
0x180001fa8  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001fad  test    al, al
0x180001faf  jnz     short loc_180001F7C
0x180001fb1  call    cs:__imp_GetLastError
0x180001fb7  test    eax, eax
0x180001fb9  jle     short loc_180001FC5
0x180001fbb  movzx   eax, ax
0x180001fbe  or      eax, 80070000h
0x180001fc3  test    eax, eax
0x180001fc5  js      short loc_18000203B
0x180001fc7  mov     eax, [rdi+30h]
0x180001fca  mov     [rsp+38h+arg_0], r12
0x180001fcf  mov     [rsp+38h+arg_8], r15
0x180001fd4  lea     ebp, [rax+rax]
0x180001fd7  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001fde  xchg    ax, ax
0x180001fe0  cmp     word ptr [rbx+rax*2+2], 0
0x180001fe6  lea     rax, [rax+1]
0x180001fea  jnz     short loc_180001FE0
0x180001fec  lea     r14d, [rax+rax]
0x180001ff0  mov     r15d, ebp
0x180001ff3  mov     eax, [rsi]
0x180001ff5  lea     rcx, [rbp+2]
0x180001ff9  mov     r12d, r14d
0x180001ffc  add     rcx, r12
0x180001fff  cmp     rax, rcx
0x180002002  jb      loc_18000210E
0x180002008  mov     rcx, [rdi+20h]
0x18000200c  mov     r8, r12; Size
0x18000200f  add     rcx, r15; void *
0x180002012  mov     rdx, rbx; Src
0x180002015  call    memcpy_0
0x18000201a  mov     rcx, [rdi+20h]
0x18000201e  lea     edx, [r14+rbp]
0x180002022  shr     edx, 1
0x180002024  xor     eax, eax
0x180002026  mov     [rdi+30h], edx
0x180002029  mov     [rcx+rdx*2], ax
0x18000202d  xor     ecx, ecx
0x18000202f  mov     r15, [rsp+38h+arg_8]
0x180002034  mov     r12, [rsp+38h+arg_0]
0x180002039  mov     eax, ecx
0x18000203b  mov     rbx, [rsp+38h+arg_10]
0x180002040  mov     rbp, [rsp+38h+arg_18]
0x180002045  add     rsp, 20h
0x180002049  pop     r14
0x18000204b  pop     rdi
0x18000204c  pop     rsi
0x18000204d  retn
0x18000204e  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180002053  jnz     loc_180001F72
0x180002059  movzx   eax, word ptr [rcx+4]
0x18000205d  cmp     ax, 3Fh ; '?'
0x180002061  jnz     loc_180002150
0x180002067  cmp     word ptr [rcx+6], 5Ch ; '\'
0x18000206c  jnz     loc_18000215A
0x180002072  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002079  nop     dword ptr [rax+00000000h]
0x180002080  cmp     word ptr [rcx+rax*2+2], 0
0x180002086  lea     rax, [rax+1]
0x18000208a  jnz     short loc_180002080
0x18000208c  mov     ecx, [rdx+28h]
0x18000208f  lea     esi, [rax+rax]
0x180002092  lea     rax, [rsi+2]
0x180002096  mov     ebp, esi
0x180002098  cmp     rcx, rax
0x18000209b  jb      short loc_1800020C1
0x18000209d  mov     rcx, [rdi+20h]; void *
0x1800020a1  mov     r8, rbp; Size
0x1800020a4  mov     rdx, rbx; Src
0x1800020a7  call    memcpy_0
0x1800020ac  mov     rcx, [rdi+20h]
0x1800020b0  xor     eax, eax
0x1800020b2  shr     esi, 1
0x1800020b4  mov     edx, esi
0x1800020b6  mov     [rdi+30h], edx
0x1800020b9  mov     [rcx+rsi*2], ax
0x1800020bd  xor     ecx, ecx
0x1800020bf  jmp     short loc_1800020FF
0x1800020c1  lea     rdx, [rsi+80h]; unsigned int
0x1800020c8  mov     eax, 0FFFFFFFFh
0x1800020cd  cmp     rdx, rax
0x1800020d0  ja      loc_180002188
0x1800020d6  mov     rcx, rdi; this
0x1800020d9  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800020de  test    al, al
0x1800020e0  jnz     short loc_18000209D
0x1800020e2  call    cs:__imp_GetLastError
0x1800020e8  mov     ecx, eax
0x1800020ea  test    eax, eax
0x1800020ec  jle     short loc_1800020F7
0x1800020ee  movzx   ecx, ax
0x1800020f1  or      ecx, 80070000h
0x1800020f7  test    ecx, ecx
0x1800020f9  js      loc_180002039
0x1800020ff  mov     rax, [rdi+20h]
0x180002103  mov     word ptr [rax+4], 3Fh ; '?'
0x180002109  jmp     loc_180002039
0x18000210e  lea     rdx, [rbp+80h]
0x180002115  mov     eax, 0FFFFFFFFh
0x18000211a  add     rdx, r12; unsigned int
0x18000211d  cmp     rdx, rax
0x180002120  ja      short loc_18000217E
0x180002122  mov     rcx, rdi; this
0x180002125  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000212a  test    al, al
0x18000212c  jnz     loc_180002008
0x180002132  call    cs:__imp_GetLastError
0x180002138  mov     ecx, eax
0x18000213a  test    eax, eax
0x18000213c  jle     loc_18000202F
0x180002142  movzx   ecx, ax
0x180002145  or      ecx, 80070000h
0x18000214b  jmp     loc_18000202F
0x180002150  cmp     ax, 2Eh ; '.'
0x180002154  jz      loc_180002067
0x18000215a  lea     rdx, aUnc_0; "\\\\?\\UNC\\"
0x180002161  mov     rcx, rdi; this
0x180002164  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002169  test    eax, eax
0x18000216b  js      loc_18000203B
0x180002171  lea     rsi, [rdi+28h]
0x180002175  add     rbx, 4
0x180002179  jmp     loc_180001FC7
0x18000217e  mov     ecx, 80070216h
0x180002183  jmp     loc_18000202F
0x180002188  mov     ecx, 80070216h
0x18000218d  jmp     loc_180002039
```
