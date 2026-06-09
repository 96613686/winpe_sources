# CHANGE_NOTIFY::CreateNotifications(void)

- ea: `0x180013fdc`
- end: `0x18001422f`
- name: `?CreateNotifications@CHANGE_NOTIFY@@AEAAJXZ`
- size: `595`
- prototype: `__int64 __fastcall(CHANGE_NOTIFY *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800143bc`

## callees

- `0x180013fdc`
- `0x180014358`
- `0x18003098e`
- `0x18003099a`

## import_xrefs

- `IisRTL!?QueryCBW@STRAU@@QEAAIXZ` at `0x1800140ed`
- `IisRTL!?QueryCBW@STRAU@@QEAAIXZ` at `0x1800140ed`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x180014056`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x180014081`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x180014056`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x180014081`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800140db`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014100`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014165`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014195`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800140db`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014100`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014165`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180014195`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800140a6`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800140a6`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014001`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800140c7`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800141f4`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014001`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800140c7`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800141f4`

## pseudocode

```c
__int64 __fastcall CHANGE_NOTIFY::CreateNotifications(CHANGE_NOTIFY *this)
{
  void *Ptr; // rax
  __int64 v4; // r12
  char *v5; // rax
  char *v6; // r15
  char *v7; // rbp
  unsigned int v8; // edi
  unsigned int CCH; // r14d
  STRAU *OriginalName; // rax
  unsigned int CBW; // edi
  void *v12; // rbx
  unsigned __int16 *StrW; // rax
  int v14; // r8d
  __int64 v15; // rdx
  STRAU *v16; // rax
  void *v17; // rdi
  STRAU *v18; // rax
  unsigned __int16 *v19; // rax
  unsigned int v20; // [rsp+60h] [rbp+8h]
  unsigned int v21; // [rsp+70h] [rbp+18h]

  if ( *((_DWORD *)this + 21) )
  {
    Ptr = BUFFER::QueryPtr((CHANGE_NOTIFY *)((char *)this + 96));
    *((_QWORD *)this + 11) = Ptr;
    if ( !Ptr )
      return 2147942414LL;
    v4 = 0;
    memset_0(Ptr, 0, 24LL * *((unsigned int *)this + 21));
    v5 = (char *)this + 144;
    v6 = (char *)*((_QWORD *)this + 18);
    while ( v6 != v5 )
    {
      v7 = v6 - 368;
      v8 = 0;
      CCH = STRAU::QueryCCH((STRAU *)(v6 - 176));
      v20 = 0;
      if ( CHANGE_ENTRY::GetOriginalName((CHANGE_ENTRY *)(v6 - 368)) )
      {
        OriginalName = CHANGE_ENTRY::GetOriginalName((CHANGE_ENTRY *)(v6 - 368));
        v8 = STRAU::QueryCCH(OriginalName);
        v20 = v8;
      }
      v21 = v8 + CCH;
      if ( !BUFFER::Resize((BUFFER *)(v7 + 312), 2 * (v8 + CCH) + 10) )
        return 2147942414LL;
      *(_DWORD *)(*((_QWORD *)this + 11) + 24 * v4 + 8) = *((_DWORD *)v7 + 4);
      *(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) = BUFFER::QueryPtr((BUFFER *)(v7 + 312));
      if ( !STRAU::QueryStrW((STRAU *)(v6 - 176)) )
        return 2147942414LL;
      CBW = STRAU::QueryCBW((STRAU *)(v6 - 176));
      v12 = *(void **)(*((_QWORD *)this + 11) + 24 * v4);
      StrW = STRAU::QueryStrW((STRAU *)(v6 - 176));
      memcpy_0(v12, StrW, CBW);
      v14 = 0;
      *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) + 2LL * CCH) = 47;
      do
      {
        v15 = v14 + CCH + 1;
        ++v14;
        *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) + 2 * v15) = 0;
      }
      while ( v14 < 2 );
      if ( CHANGE_ENTRY::GetOriginalName((CHANGE_ENTRY *)(v6 - 368)) )
      {
        v16 = CHANGE_ENTRY::GetOriginalName((CHANGE_ENTRY *)(v6 - 368));
        if ( !STRAU::QueryStrW(v16) )
          return 2147942414LL;
        v17 = (void *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) + 2LL * (CCH + 2));
        v18 = CHANGE_ENTRY::GetOriginalName((CHANGE_ENTRY *)(v6 - 368));
        v19 = STRAU::QueryStrW(v18);
        memcpy_0(v17, v19, 2LL * v20);
        *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) + 2LL * (v21 + 2)) = 47;
        *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4) + 2LL * (v21 + 3)) = 0;
      }
      *(_DWORD *)(*((_QWORD *)this + 11) + 24 * v4 + 12) = *((_DWORD *)v7 + 5);
      *(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4 + 16) = 0;
      if ( *((_DWORD *)v7 + 5) )
        *(_QWORD *)(*((_QWORD *)this + 11) + 24 * v4 + 16) = BUFFER::QueryPtr((BUFFER *)(v7 + 24));
      v6 = *(char **)v6;
      v5 = (char *)this + 144;
      v4 = (unsigned int)(v4 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013fdc  mov     [rsp+arg_18], rbx
0x180013fe1  push    rbp
0x180013fe2  push    rsi
0x180013fe3  push    rdi
0x180013fe4  push    r12
0x180013fe6  push    r13
0x180013fe8  push    r14
0x180013fea  push    r15
0x180013fec  sub     rsp, 20h
0x180013ff0  cmp     dword ptr [rcx+54h], 0
0x180013ff4  mov     rsi, rcx
0x180013ff7  jz      loc_180014218
0x180013ffd  add     rcx, 60h ; '`'
0x180014001  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014007  mov     [rsi+58h], rax
0x18001400b  mov     rcx, rax; void *
0x18001400e  test    rax, rax
0x180014011  jnz     short loc_18001401D
0x180014013  mov     eax, 8007000Eh
0x180014018  jmp     loc_18001421A
0x18001401d  mov     eax, [rsi+54h]
0x180014020  xor     r12d, r12d
0x180014023  xor     edx, edx; Val
0x180014025  lea     r8, [rax+rax*2]
0x180014029  shl     r8, 3; Size
0x18001402d  call    memset_0
0x180014032  lea     rax, [rsi+90h]
0x180014039  mov     r15, [rax]
0x18001403c  cmp     r15, rax
0x18001403f  jz      loc_180014218
0x180014045  lea     rbp, [r15-170h]
0x18001404c  lea     r13, [rbp+0C0h]
0x180014053  mov     rcx, r13
0x180014056  call    cs:__imp_?QueryCCH@STRAU@@QEAAIXZ; STRAU::QueryCCH(void)
0x18001405c  xor     edi, edi
0x18001405e  mov     rcx, rbp; this
0x180014061  mov     r14d, eax
0x180014064  mov     [rsp+58h+arg_8], eax
0x180014068  mov     [rsp+58h+arg_0], edi
0x18001406c  call    ?GetOriginalName@CHANGE_ENTRY@@QEAAPEAVSTRAU@@XZ; CHANGE_ENTRY::GetOriginalName(void)
0x180014071  test    rax, rax
0x180014074  jz      short loc_18001408D
0x180014076  mov     rcx, rbp; this
0x180014079  call    ?GetOriginalName@CHANGE_ENTRY@@QEAAPEAVSTRAU@@XZ; CHANGE_ENTRY::GetOriginalName(void)
0x18001407e  mov     rcx, rax
0x180014081  call    cs:__imp_?QueryCCH@STRAU@@QEAAIXZ; STRAU::QueryCCH(void)
0x180014087  mov     edi, eax
0x180014089  mov     [rsp+58h+arg_0], eax
0x18001408d  lea     eax, [rdi+r14]
0x180014091  lea     rbx, [rbp+138h]
0x180014098  mov     [rsp+58h+arg_10], eax
0x18001409c  lea     edx, ds:0Ah[rax*2]
0x1800140a3  mov     rcx, rbx
0x1800140a6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800140ac  test    al, al
0x1800140ae  jz      loc_180014013
0x1800140b4  mov     rdx, [rsi+58h]
0x1800140b8  lea     r14, [r12+r12*2]
0x1800140bc  mov     eax, [rbp+10h]
0x1800140bf  mov     rcx, rbx
0x1800140c2  mov     [rdx+r14*8+8], eax
0x1800140c7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800140cd  mov     rdx, rax
0x1800140d0  mov     rcx, r13
0x1800140d3  mov     rax, [rsi+58h]
0x1800140d7  mov     [rax+r14*8], rdx
0x1800140db  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x1800140e1  test    rax, rax
0x1800140e4  jz      loc_180014013
0x1800140ea  mov     rcx, r13
0x1800140ed  call    cs:__imp_?QueryCBW@STRAU@@QEAAIXZ; STRAU::QueryCBW(void)
0x1800140f3  mov     edi, eax
0x1800140f5  mov     rcx, r13
0x1800140f8  mov     rax, [rsi+58h]
0x1800140fc  mov     rbx, [rax+r14*8]
0x180014100  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x180014106  mov     r8d, edi; Size
0x180014109  mov     rcx, rbx; void *
0x18001410c  mov     rdx, rax; Src
0x18001410f  call    memcpy_0
0x180014114  mov     rax, [rsi+58h]
0x180014118  mov     r13d, 2Fh ; '/'
0x18001411e  mov     ebx, [rsp+58h+arg_8]
0x180014122  xor     r8d, r8d
0x180014125  mov     rcx, [rax+r14*8]
0x180014129  lea     r9d, [rbx+1]
0x18001412d  mov     [rcx+rbx*2], r13w
0x180014132  mov     rax, [rsi+58h]
0x180014136  lea     edx, [r8+r9]
0x18001413a  inc     r8d
0x18001413d  mov     rcx, [rax+r14*8]
0x180014141  xor     eax, eax
0x180014143  mov     [rcx+rdx*2], ax
0x180014147  cmp     r8d, 2
0x18001414b  jl      short loc_180014132
0x18001414d  mov     rcx, rbp; this
0x180014150  call    ?GetOriginalName@CHANGE_ENTRY@@QEAAPEAVSTRAU@@XZ; CHANGE_ENTRY::GetOriginalName(void)
0x180014155  test    rax, rax
0x180014158  jz      short loc_1800141D1
0x18001415a  mov     rcx, rbp; this
0x18001415d  call    ?GetOriginalName@CHANGE_ENTRY@@QEAAPEAVSTRAU@@XZ; CHANGE_ENTRY::GetOriginalName(void)
0x180014162  mov     rcx, rax
0x180014165  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001416b  test    rax, rax
0x18001416e  jz      loc_180014013
0x180014174  mov     rax, [rsi+58h]
0x180014178  lea     edx, [rbx+2]
0x18001417b  mov     ebx, [rsp+58h+arg_0]
0x18001417f  add     rbx, rbx
0x180014182  mov     rcx, [rax+r14*8]
0x180014186  lea     rdi, [rcx+rdx*2]
0x18001418a  mov     rcx, rbp; this
0x18001418d  call    ?GetOriginalName@CHANGE_ENTRY@@QEAAPEAVSTRAU@@XZ; CHANGE_ENTRY::GetOriginalName(void)
0x180014192  mov     rcx, rax
0x180014195  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001419b  mov     r8, rbx; Size
0x18001419e  mov     rcx, rdi; void *
0x1800141a1  mov     rdx, rax; Src
0x1800141a4  call    memcpy_0
0x1800141a9  mov     rax, [rsi+58h]
0x1800141ad  mov     r8d, [rsp+58h+arg_10]
0x1800141b2  mov     rcx, [rax+r14*8]
0x1800141b6  lea     edx, [r8+2]
0x1800141ba  mov     [rcx+rdx*2], r13w
0x1800141bf  lea     edx, [r8+3]
0x1800141c3  mov     rax, [rsi+58h]
0x1800141c7  mov     rcx, [rax+r14*8]
0x1800141cb  xor     eax, eax
0x1800141cd  mov     [rcx+rdx*2], ax
0x1800141d1  mov     eax, [rbp+14h]
0x1800141d4  mov     rcx, [rsi+58h]
0x1800141d8  mov     [rcx+r14*8+0Ch], eax
0x1800141dd  mov     rax, [rsi+58h]
0x1800141e1  mov     qword ptr [rax+r14*8+10h], 0
0x1800141ea  cmp     dword ptr [rbp+14h], 0
0x1800141ee  jz      short loc_180014206
0x1800141f0  lea     rcx, [rbp+18h]
0x1800141f4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800141fa  mov     rcx, rax
0x1800141fd  mov     rax, [rsi+58h]
0x180014201  mov     [rax+r14*8+10h], rcx
0x180014206  mov     r15, [r15]
0x180014209  lea     rax, [rsi+90h]
0x180014210  inc     r12d
0x180014213  jmp     loc_18001403C
0x180014218  xor     eax, eax
0x18001421a  mov     rbx, [rsp+58h+arg_18]
0x18001421f  add     rsp, 20h
0x180014223  pop     r15
0x180014225  pop     r14
0x180014227  pop     r13
0x180014229  pop     r12
0x18001422b  pop     rdi
0x18001422c  pop     rsi
0x18001422d  pop     rbp
0x18001422e  retn
```
