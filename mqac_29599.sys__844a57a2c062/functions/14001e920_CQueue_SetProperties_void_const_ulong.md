# CQueue::SetProperties(void const *,ulong)

- ea: `0x14001e920`
- end: `0x14001ea96`
- name: `?SetProperties@CQueue@@UEAAJPEBXK@Z`
- size: `374`
- prototype: `__int64 __fastcall(CQueue *__hidden this, const void *Address, SIZE_T Length)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14001caf0`
- `0x14001e920`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14001e952`
- `ntoskrnl!ProbeForRead` at `0x14001e9a7`
- `ntoskrnl!ProbeForRead` at `0x14001e952`
- `ntoskrnl!ProbeForRead` at `0x14001e9a7`

## pseudocode

```c
__int64 __fastcall CQueue::SetProperties(CQueue *this, int *Address, SIZE_T Length)
{
  __int128 *v5; // r15
  int v6; // esi
  int v7; // r14d
  int v8; // r12d
  int v9; // r13d
  __int128 *v10; // rbx
  const struct _GUID *v11; // rdx
  int v12; // r9d
  unsigned int v13; // r10d
  unsigned int v14; // r11d
  int v15; // ecx
  char v16; // r8
  __int64 v17; // rcx
  int v18; // esi
  __int128 v20; // [rsp+28h] [rbp-40h] BYREF

  v5 = 0;
  v20 = 0;
  ProbeForRead(Address, (unsigned int)Length, 1u);
  v6 = *Address;
  v7 = Address[1];
  v8 = Address[5];
  v9 = Address[6];
  v10 = (__int128 *)*((_QWORD *)Address + 4);
  if ( v10 )
  {
    ProbeForRead(v10, 0x10u, 1u);
    v20 = *v10;
    v5 = v10;
  }
  if ( v5 )
    v11 = (const struct _GUID *)&v20;
  else
    v11 = 0;
  CQueue::ConnectorQM(this, v11);
  v15 = *((_DWORD *)this + 14) ^ ((unsigned __int8)*((_DWORD *)this + 14) ^ (unsigned __int8)(2 * v9)) & 2;
  *((_DWORD *)this + 14) = v15;
  *((_DWORD *)this + 14) = v15 ^ ((unsigned __int8)v15 ^ (unsigned __int8)(4 * v16)) & 4;
  *((_DWORD *)this + 49) = v8;
  v17 = *((_QWORD *)this + 19);
  if ( v17 )
  {
    v18 = *((_DWORD *)this + 42) ^ ((unsigned __int8)*((_DWORD *)this + 42) ^ (unsigned __int8)(16 * v6)) & 0x10;
    *((_DWORD *)this + 42) = v18;
    *((_QWORD *)this + 22) = (unsigned __int64)v13 << 10;
    *((_DWORD *)this + 42) = v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)((_WORD)v7 << 8)) & 0x100;
    *((_DWORD *)this + 60) = v12;
    *(_QWORD *)(v17 + 176) = (unsigned __int64)v14 << 10;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e920  mov     [rsp+arg_0], rbx
0x14001e925  mov     [rsp+arg_10], rsi
0x14001e92a  push    rdi
0x14001e92b  push    r12
0x14001e92d  push    r13
0x14001e92f  push    r14
0x14001e931  push    r15
0x14001e933  sub     rsp, 40h
0x14001e937  mov     rbx, rdx
0x14001e93a  mov     rdi, rcx
0x14001e93d  xor     r15d, r15d
0x14001e940  xorps   xmm0, xmm0
0x14001e943  movups  [rsp+68h+var_40], xmm0
0x14001e948  mov     edx, r8d; Length
0x14001e94b  lea     r8d, [r15+1]; Alignment
0x14001e94f  mov     rcx, rbx; Address
0x14001e952  call    cs:__imp_ProbeForRead
0x14001e959  nop     dword ptr [rax+rax+00h]
0x14001e95e  mov     esi, [rbx]
0x14001e960  mov     r14d, [rbx+4]
0x14001e964  mov     r9d, [rbx+8]
0x14001e968  mov     [rsp+68h+arg_18], r9d
0x14001e970  mov     r10d, [rbx+0Ch]
0x14001e974  mov     [rsp+68h+var_48], r10d
0x14001e979  mov     r11d, [rbx+10h]
0x14001e97d  mov     [rsp+68h+var_44], r11d
0x14001e982  mov     r12d, [rbx+14h]
0x14001e986  mov     r13d, [rbx+18h]
0x14001e98a  mov     r8d, [rbx+1Ch]
0x14001e98e  mov     [rsp+68h+arg_8], r8d
0x14001e993  mov     rbx, [rbx+20h]
0x14001e997  test    rbx, rbx
0x14001e99a  jz      short loc_14001E9D6
0x14001e99c  lea     edx, [r15+10h]; Length
0x14001e9a0  lea     r8d, [r15+1]; Alignment
0x14001e9a4  mov     rcx, rbx; Address
0x14001e9a7  call    cs:__imp_ProbeForRead
0x14001e9ae  nop     dword ptr [rax+rax+00h]
0x14001e9b3  movups  xmm0, xmmword ptr [rbx]
0x14001e9b6  movdqu  [rsp+68h+var_40], xmm0
0x14001e9bc  mov     r15, rbx
0x14001e9bf  mov     r8d, [rsp+68h+arg_8]
0x14001e9c4  mov     r9d, [rsp+68h+arg_18]
0x14001e9cc  mov     r10d, [rsp+68h+var_48]
0x14001e9d1  mov     r11d, [rsp+68h+var_44]
0x14001e9d6  mov     rcx, rdi; this
0x14001e9d9  test    r15, r15
0x14001e9dc  jz      short loc_14001E9E5
0x14001e9de  lea     rdx, [rsp+68h+var_40]
0x14001e9e3  jmp     short loc_14001E9E7
0x14001e9e5  xor     edx, edx; struct _GUID *
0x14001e9e7  call    ?ConnectorQM@CQueue@@AEAAXPEBU_GUID@@@Z; CQueue::ConnectorQM(_GUID const *)
0x14001e9ec  mov     eax, [rdi+38h]
0x14001e9ef  lea     ecx, ds:0[r13*2]
0x14001e9f7  xor     ecx, eax
0x14001e9f9  and     ecx, 2
0x14001e9fc  xor     ecx, eax
0x14001e9fe  mov     [rdi+38h], ecx
0x14001ea01  lea     eax, ds:0[r8*4]
0x14001ea09  xor     eax, ecx
0x14001ea0b  and     eax, 4
0x14001ea0e  xor     eax, ecx
0x14001ea10  mov     [rdi+38h], eax
0x14001ea13  mov     [rdi+0C4h], r12d
0x14001ea1a  mov     rcx, [rdi+98h]
0x14001ea21  test    rcx, rcx
0x14001ea24  jz      short loc_14001EA77
0x14001ea26  mov     eax, [rdi+0A8h]
0x14001ea2c  shl     esi, 4
0x14001ea2f  xor     esi, eax
0x14001ea31  and     esi, 10h
0x14001ea34  xor     esi, eax
0x14001ea36  mov     [rdi+0A8h], esi
0x14001ea3c  mov     eax, r10d
0x14001ea3f  shl     rax, 0Ah
0x14001ea43  mov     [rdi+0B0h], rax
0x14001ea4a  shl     r14d, 8
0x14001ea4e  xor     r14d, esi
0x14001ea51  and     r14d, 100h
0x14001ea58  xor     r14d, esi
0x14001ea5b  mov     [rdi+0A8h], r14d
0x14001ea62  mov     [rdi+0F0h], r9d
0x14001ea69  mov     eax, r11d
0x14001ea6c  shl     rax, 0Ah
0x14001ea70  mov     [rcx+0B0h], rax
0x14001ea77  xor     eax, eax
0x14001ea79  jmp     short $+2
0x14001ea7b  lea     r11, [rsp+68h+var_28]
0x14001ea80  mov     rbx, [r11+30h]
0x14001ea84  mov     rsi, [r11+40h]
0x14001ea88  mov     rsp, r11
0x14001ea8b  pop     r15
0x14001ea8d  pop     r14
0x14001ea8f  pop     r13
0x14001ea91  pop     r12
0x14001ea93  pop     rdi
0x14001ea94  retn
```
