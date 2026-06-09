# CDirectMusic::CreateMusicBuffer(_DMUS_BUFFERDESC *,IDirectMusicBuffer * *,IUnknown *)

- ea: `0x180013050`
- end: `0x18001318b`
- name: `?CreateMusicBuffer@CDirectMusic@@UEAAJPEAU_DMUS_BUFFERDESC@@PEAPEAUIDirectMusicBuffer@@PEAUIUnknown@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CDirectMusic *__hidden this, struct _DMUS_BUFFERDESC *, struct IDirectMusicBuffer **, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x18000a0ac`
- `0x180013050`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800130a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800130a1`

## pseudocode

```c
__int64 __fastcall CDirectMusic::CreateMusicBuffer(
        CDirectMusic *this,
        struct _DMUS_BUFFERDESC *a2,
        struct IDirectMusicBuffer **a3,
        struct IUnknown *a4)
{
  char *v7; // rbx
  __int128 v8; // xmm1
  unsigned __int64 v9; // rcx
  void *v10; // rax

  if ( !a2 || a2->dwSize < 0x1C )
    return 2147942487LL;
  if ( !a3 )
    return 2147500035LL;
  if ( a4 )
    return 2147746064LL;
  *a3 = 0;
  v7 = (char *)malloc(0x58u);
  if ( !v7 )
    return 2147942414LL;
  *(_QWORD *)v7 = &CDirectMusicBuffer::`vftable';
  *(_OWORD *)(v7 + 52) = *(_OWORD *)&a2->dwSize;
  v8 = *(_OWORD *)&a2->guidBufferFormat.Data2;
  *((_DWORD *)v7 + 2) = 1;
  *((_QWORD *)v7 + 4) = 0;
  *((_OWORD *)v7 + 4) = v8;
  v9 = (*((_DWORD *)v7 + 19) + 3) & 0xFFFFFFFC;
  *((_DWORD *)v7 + 10) = v9;
  v10 = operator new[](v9);
  *((_QWORD *)v7 + 4) = v10;
  if ( !v10 )
  {
    CDirectMusicBuffer::~CDirectMusicBuffer((CDirectMusicBuffer *)v7);
    operator delete(v7);
    return 2147942414LL;
  }
  *(_QWORD *)(v7 + 44) = 0;
  *((_QWORD *)v7 + 3) = 0;
  if ( *(_QWORD *)(v7 + 60) == *(_QWORD *)&GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
    && *(_QWORD *)(v7 + 68) == *(_QWORD *)GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data4
    || !*(_QWORD *)(v7 + 60) && !*(_QWORD *)(v7 + 68) )
  {
    *(GUID *)(v7 + 60) = GUID_1d262760_e957_11cf_a5d6_28db04c10000;
  }
  *a3 = (struct IDirectMusicBuffer *)v7;
  return 0;
}

```

## disassembly

```asm
0x180013050  mov     [rsp+arg_0], rbx
0x180013055  mov     [rsp+arg_10], rsi
0x18001305a  push    rdi
0x18001305b  sub     rsp, 20h
0x18001305f  mov     rdi, r8
0x180013062  mov     rsi, rdx
0x180013065  test    rdx, rdx
0x180013068  jz      loc_180013176
0x18001306e  cmp     dword ptr [rdx], 1Ch
0x180013071  jb      loc_180013176
0x180013077  test    r8, r8
0x18001307a  jnz     short loc_180013086
0x18001307c  mov     eax, 80004003h
0x180013081  jmp     loc_18001317B
0x180013086  test    r9, r9
0x180013089  jz      short loc_180013095
0x18001308b  mov     eax, 80040110h
0x180013090  jmp     loc_18001317B
0x180013095  mov     ecx, 58h ; 'X'; Size
0x18001309a  mov     qword ptr [r8], 0
0x1800130a1  call    cs:__imp_malloc
0x1800130a7  mov     [rsp+28h+arg_8], rax
0x1800130ac  mov     rbx, rax
0x1800130af  test    rax, rax
0x1800130b2  jz      loc_18001316F
0x1800130b8  lea     rax, ??_7CDirectMusicBuffer@@6B@; const CDirectMusicBuffer::`vftable'
0x1800130bf  mov     [rbx], rax
0x1800130c2  movups  xmm0, xmmword ptr [rsi]
0x1800130c5  movups  xmmword ptr [rbx+34h], xmm0
0x1800130c9  movups  xmm1, xmmword ptr [rsi+0Ch]
0x1800130cd  mov     dword ptr [rbx+8], 1
0x1800130d4  mov     qword ptr [rbx+20h], 0
0x1800130dc  movups  xmmword ptr [rbx+40h], xmm1
0x1800130e0  test    rbx, rbx
0x1800130e3  jz      loc_18001316F
0x1800130e9  mov     ecx, [rbx+4Ch]
0x1800130ec  add     ecx, 3
0x1800130ef  and     ecx, 0FFFFFFFCh; unsigned __int64
0x1800130f2  mov     [rbx+28h], ecx
0x1800130f5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800130fa  mov     [rbx+20h], rax
0x1800130fe  test    rax, rax
0x180013101  jz      short loc_18001315A
0x180013103  mov     qword ptr [rbx+2Ch], 0
0x18001310b  mov     qword ptr [rbx+18h], 0
0x180013113  mov     rax, [rbx+3Ch]
0x180013117  cmp     rax, qword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data1
0x18001311e  jnz     short loc_18001312D
0x180013120  mov     rax, [rbx+44h]
0x180013124  cmp     rax, qword ptr cs:_GUID_e725d360_62cc_11cf_a5d6_28db04c10000.Data4
0x18001312b  jz      short loc_180013147
0x18001312d  mov     rax, [rbx+3Ch]
0x180013131  cmp     rax, cs:qword_1800254C0
0x180013138  jnz     short loc_180013153
0x18001313a  mov     rax, [rbx+44h]
0x18001313e  cmp     rax, cs:qword_1800254C8
0x180013145  jnz     short loc_180013153
0x180013147  movups  xmm0, xmmword ptr cs:_GUID_1d262760_e957_11cf_a5d6_28db04c10000.Data1
0x18001314e  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x180013153  mov     [rdi], rbx
0x180013156  xor     eax, eax
0x180013158  jmp     short loc_18001317B
0x18001315a  mov     rcx, rbx; this
0x18001315d  call    ??1CDirectMusicBuffer@@QEAA@XZ; CDirectMusicBuffer::~CDirectMusicBuffer(void)
0x180013162  mov     edx, 58h ; 'X'; unsigned __int64
0x180013167  mov     rcx, rbx; void *
0x18001316a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001316f  mov     eax, 8007000Eh
0x180013174  jmp     short loc_18001317B
0x180013176  mov     eax, 80070057h
0x18001317b  mov     rbx, [rsp+28h+arg_0]
0x180013180  mov     rsi, [rsp+28h+arg_10]
0x180013185  add     rsp, 20h
0x180013189  pop     rdi
0x18001318a  retn
```
