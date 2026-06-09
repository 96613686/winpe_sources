# CreateIniTnFilter

- ea: `0x180031190`
- end: `0x1800313dc`
- name: `CreateIniTnFilter`
- size: `588`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800303b8`
- `0x180032b84`

## callees

- `0x180006f00`
- `0x18000e510`
- `0x18001642c`
- `0x180019e74`
- `0x180031190`
- `0x1800324b4`
- `0x180042f28`

## pseudocode

```c
__int64 __fastcall CreateIniTnFilter(__int64 a1, __int128 *a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned int v9; // ebp
  _QWORD *v10; // rcx
  __int64 v11; // rsi
  _QWORD *v12; // r14
  unsigned int v13; // eax
  __int64 result; // rax
  __int128 v15; // xmm0

  v7 = IpsecAllocMem(368);
  v8 = v7;
  if ( !v7 )
  {
    v9 = 14;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, 14);
      v10 = WPP_GLOBAL_Control;
    }
    v11 = a1 + 4;
    v12 = (_QWORD *)(a1 + 24);
    goto LABEL_10;
  }
  *(_QWORD *)(v7 + 236) = 0;
  v11 = a1 + 4;
  *(_DWORD *)(v7 + 244) = 0;
  v12 = (_QWORD *)(a1 + 24);
  *(_DWORD *)v7 = *(_DWORD *)a1;
  *(_OWORD *)(v7 + 4) = *(_OWORD *)(a1 + 4);
  v13 = NsuStringDupW(v7 + 24, 0, *(_QWORD *)(a1 + 24));
  v9 = v13;
  if ( v13 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_13:
      if ( v8 )
        FreeIniTnFilter((LPVOID)v8);
      *a5 = 0;
      return v9;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, v13);
      v10 = WPP_GLOBAL_Control;
    }
LABEL_10:
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
      WPP_SF_S_guid_D(v10[2], 29, (unsigned int)WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids, *v12, v11, v9);
    goto LABEL_13;
  }
  *(_DWORD *)(v8 + 32) = *(_DWORD *)(a1 + 32);
  *(_DWORD *)(v8 + 36) = *(_DWORD *)(a1 + 36);
  *(_DWORD *)(v8 + 40) = *(_DWORD *)(a1 + 40);
  CopyOldExtToIntAddresses(*(_DWORD *)a1, a1 + 48, v8 + 44);
  CopyOldExtToIntAddresses(*(_DWORD *)a1, a1 + 80, v8 + 84);
  CopyOldExtToIntAddresses(*(_DWORD *)a1, a1 + 136, v8 + 124);
  CopyOldExtToIntAddresses(*(_DWORD *)a1, a1 + 168, v8 + 164);
  *(_DWORD *)(v8 + 212) = 1;
  *(_WORD *)(v8 + 216) = *(_WORD *)(a1 + 124);
  *(_WORD *)(v8 + 218) = 0;
  *(_DWORD *)(v8 + 220) = 1;
  *(_WORD *)(v8 + 224) = *(_WORD *)(a1 + 132);
  *(_WORD *)(v8 + 226) = 0;
  *(_QWORD *)(v8 + 204) = *(_QWORD *)(a1 + 112);
  *(_DWORD *)(v8 + 228) = *(_DWORD *)(a1 + 200);
  *(_DWORD *)(v8 + 232) = *(_DWORD *)(a1 + 204);
  if ( a2 )
    v15 = *a2;
  else
    v15 = *(_OWORD *)(a1 + 216);
  *(_OWORD *)(v8 + 248) = v15;
  *(_QWORD *)(v8 + 264) = 0;
  *(_QWORD *)(v8 + 296) = 0;
  *a5 = v8;
  result = 0;
  *(_QWORD *)(v8 + 304) = 0;
  *(_QWORD *)(v8 + 352) = 0;
  *(_DWORD *)(v8 + 360) = 0;
  *(_DWORD *)(v8 + 272) = 0;
  *(_QWORD *)(v8 + 280) = 0;
  *(_QWORD *)(v8 + 288) = 0;
  return result;
}

```

## disassembly

```asm
0x180031190  push    rbx
0x180031192  push    rbp
0x180031193  push    rsi
0x180031194  push    rdi
0x180031195  push    r12
0x180031197  push    r14
0x180031199  push    r15
0x18003119b  sub     rsp, 30h
0x18003119f  mov     rdi, rcx
0x1800311a2  mov     r15, rdx
0x1800311a5  mov     ecx, 170h
0x1800311aa  call    IpsecAllocMem
0x1800311af  xor     r12d, r12d
0x1800311b2  mov     rbx, rax
0x1800311b5  test    rax, rax
0x1800311b8  jnz     short loc_1800311FD
0x1800311ba  lea     ebp, [rax+0Eh]
0x1800311bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311c4  lea     r15, WPP_GLOBAL_Control
0x1800311cb  cmp     rcx, r15
0x1800311ce  jz      short loc_1800311F3
0x1800311d0  test    byte ptr [rcx+1Ch], 10h
0x1800311d4  jz      short loc_1800311F3
0x1800311d6  mov     rcx, [rcx+10h]
0x1800311da  lea     edx, [rax+1Bh]
0x1800311dd  mov     r9d, ebp
0x1800311e0  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x1800311e7  call    WPP_SF_d
0x1800311ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311f3  lea     rsi, [rdi+4]
0x1800311f7  lea     r14, [rdi+18h]
0x1800311fb  jmp     short loc_18003126F
0x1800311fd  mov     [rax+0ECh], r12
0x180031204  lea     rsi, [rdi+4]
0x180031208  mov     [rax+0F4h], r12d
0x18003120f  lea     r14, [rdi+18h]
0x180031213  mov     eax, [rdi]
0x180031215  lea     rcx, [rbx+18h]
0x180031219  mov     [rbx], eax
0x18003121b  xor     edx, edx
0x18003121d  movups  xmm0, xmmword ptr [rsi]
0x180031220  movdqu  xmmword ptr [rbx+4], xmm0
0x180031225  mov     r8, [r14]
0x180031228  call    NsuStringDupW
0x18003122d  mov     ebp, eax
0x18003122f  test    eax, eax
0x180031231  jz      loc_1800312BA
0x180031237  mov     rcx, cs:WPP_GLOBAL_Control
0x18003123e  lea     r15, WPP_GLOBAL_Control
0x180031245  cmp     rcx, r15
0x180031248  jz      short loc_18003129B
0x18003124a  test    byte ptr [rcx+1Ch], 10h
0x18003124e  jz      short loc_18003126F
0x180031250  mov     rcx, [rcx+10h]
0x180031254  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x18003125b  mov     edx, 1Ch
0x180031260  mov     r9d, eax
0x180031263  call    WPP_SF_d
0x180031268  mov     rcx, cs:WPP_GLOBAL_Control
0x18003126f  cmp     rcx, r15
0x180031272  jz      short loc_18003129B
0x180031274  test    byte ptr [rcx+1Ch], 10h
0x180031278  jz      short loc_18003129B
0x18003127a  mov     r9, [r14]
0x18003127d  lea     r8, WPP_393a1e518f2e3ec1fd8734a3be6eb9ff_Traceguids
0x180031284  mov     rcx, [rcx+10h]
0x180031288  mov     edx, 1Dh
0x18003128d  mov     [rsp+68h+var_40], ebp
0x180031291  mov     [rsp+68h+var_48], rsi
0x180031296  call    WPP_SF_S_guid_D
0x18003129b  test    rbx, rbx
0x18003129e  jz      short loc_1800312A8
0x1800312a0  mov     rcx, rbx; lpMem
0x1800312a3  call    FreeIniTnFilter
0x1800312a8  mov     rax, [rsp+68h+arg_20]
0x1800312b0  mov     [rax], r12
0x1800312b3  mov     eax, ebp
0x1800312b5  jmp     loc_1800313CD
0x1800312ba  mov     eax, [rdi+20h]
0x1800312bd  lea     r8, [rbx+2Ch]
0x1800312c1  mov     [rbx+20h], eax
0x1800312c4  lea     rdx, [rdi+30h]
0x1800312c8  mov     eax, [rdi+24h]
0x1800312cb  mov     [rbx+24h], eax
0x1800312ce  mov     eax, [rdi+28h]
0x1800312d1  mov     [rbx+28h], eax
0x1800312d4  mov     ecx, [rdi]
0x1800312d6  call    CopyOldExtToIntAddresses
0x1800312db  mov     ecx, [rdi]
0x1800312dd  lea     r8, [rbx+54h]
0x1800312e1  lea     rdx, [rdi+50h]
0x1800312e5  call    CopyOldExtToIntAddresses
0x1800312ea  mov     ecx, [rdi]
0x1800312ec  lea     r8, [rbx+7Ch]
0x1800312f0  lea     rdx, [rdi+88h]
0x1800312f7  call    CopyOldExtToIntAddresses
0x1800312fc  mov     ecx, [rdi]
0x1800312fe  lea     r8, [rbx+0A4h]
0x180031305  lea     rdx, [rdi+0A8h]
0x18003130c  call    CopyOldExtToIntAddresses
0x180031311  mov     ecx, 1
0x180031316  mov     [rbx+0D4h], ecx
0x18003131c  movzx   eax, word ptr [rdi+7Ch]
0x180031320  mov     [rbx+0D8h], ax
0x180031327  mov     [rbx+0DAh], r12w
0x18003132f  mov     [rbx+0DCh], ecx
0x180031335  movzx   eax, word ptr [rdi+84h]
0x18003133c  mov     [rbx+0E0h], ax
0x180031343  mov     [rbx+0E2h], r12w
0x18003134b  mov     rax, [rdi+70h]
0x18003134f  mov     [rbx+0CCh], rax
0x180031356  mov     eax, [rdi+0C8h]
0x18003135c  mov     [rbx+0E4h], eax
0x180031362  mov     eax, [rdi+0CCh]
0x180031368  mov     [rbx+0E8h], eax
0x18003136e  test    r15, r15
0x180031371  jz      short loc_180031379
0x180031373  movups  xmm0, xmmword ptr [r15]
0x180031377  jmp     short loc_180031380
0x180031379  movups  xmm0, xmmword ptr [rdi+0D8h]
0x180031380  mov     rax, [rsp+68h+arg_20]
0x180031388  movdqu  xmmword ptr [rbx+0F8h], xmm0
0x180031390  mov     [rbx+108h], r12
0x180031397  mov     [rbx+128h], r12
0x18003139e  mov     [rax], rbx
0x1800313a1  xor     eax, eax
0x1800313a3  mov     [rbx+130h], r12
0x1800313aa  mov     [rbx+160h], r12
0x1800313b1  mov     [rbx+168h], r12d
0x1800313b8  mov     [rbx+110h], r12d
0x1800313bf  mov     [rbx+118h], r12
0x1800313c6  mov     [rbx+120h], r12
0x1800313cd  add     rsp, 30h
0x1800313d1  pop     r15
0x1800313d3  pop     r14
0x1800313d5  pop     r12
0x1800313d7  pop     rdi
0x1800313d8  pop     rsi
0x1800313d9  pop     rbp
0x1800313da  pop     rbx
0x1800313db  retn
```
