# FIETWLogMdlReadWrite

- ea: `0x140002708`
- end: `0x1400028c1`
- name: `FIETWLogMdlReadWrite`
- size: `441`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400026d0`
- `0x140002a80`

## callees

- `0x140002708`
- `0x140003920`
- `0x140003a00`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400027ca`
- `ntoskrnl!PsGetThreadId` at `0x1400027ca`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140002804`
- `FLTMGR!FltGetActivityIdCallbackData` at `0x140002804`

## pseudocode

```c
char __fastcall FIETWLogMdlReadWrite(__int64 a1, __int64 a2)
{
  char result; // al
  __int64 (__fastcall *v5)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *); // rsi
  __int64 v6; // rcx
  __int64 *v7; // rdx
  int v8; // ecx
  __int16 v9; // bx
  struct _KTHREAD *v10; // rcx
  unsigned int ThreadId; // eax
  __int64 v12; // rax
  int ActivityIdCallbackData; // eax
  __int128 *v14; // rdx
  __int128 v15; // [rsp+40h] [rbp-19h] BYREF
  __int128 v16; // [rsp+50h] [rbp-9h]
  __int128 v17; // [rsp+60h] [rbp+7h]
  __int128 v18; // [rsp+70h] [rbp+17h] BYREF
  _QWORD v19[2]; // [rsp+80h] [rbp+27h] BYREF

  result = qword_140009A00;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v5 = *(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64, __int64, __int16, __int128 *))(qword_140009A00 + 16);
  if ( v5 )
  {
    v6 = *(_QWORD *)(a1 + 16);
    v15 = 0;
    v16 = 0;
    v17 = 0;
    if ( *(_BYTE *)(v6 + 4) == 3 || *(_BYTE *)(v6 + 4) == 4 )
    {
      result = *(_BYTE *)(v6 + 5) & 4;
      if ( *(_BYTE *)(v6 + 4) == 3 )
      {
        if ( result )
          return result;
        v9 = 1091;
      }
      else
      {
        if ( !result )
          return result;
        v9 = 1092;
      }
      *(_QWORD *)&v15 = *(_QWORD *)(v6 + 40);
      DWORD1(v17) = *(_DWORD *)(v6 + 24);
      DWORD2(v17) = *(_DWORD *)v6;
    }
    else if ( *(unsigned __int8 *)(v6 + 4) == 238 )
    {
      *(_QWORD *)&v15 = *(_QWORD *)(v6 + 24);
      v7 = *(__int64 **)(v6 + 32);
      if ( v7 )
      {
        v8 = 0;
        do
        {
          v8 += *((_DWORD *)v7 + 10);
          DWORD1(v17) = v8;
          v7 = (__int64 *)*v7;
        }
        while ( v7 );
      }
      v9 = 1092;
    }
    else
    {
      if ( *(unsigned __int8 *)(v6 + 4) != 241 )
        return result;
      v9 = 1091;
      *(_QWORD *)&v15 = *(_QWORD *)(v6 + 24);
      DWORD1(v17) = *(_DWORD *)(v6 + 32);
    }
    v10 = *(struct _KTHREAD **)(a1 + 8);
    *((_QWORD *)&v15 + 1) = a1;
    if ( v10 )
      ThreadId = (unsigned int)PsGetThreadId(v10);
    else
      ThreadId = -1;
    LODWORD(v17) = ThreadId;
    *(_QWORD *)&v16 = *(_QWORD *)(a2 + 32);
    v12 = *(_QWORD *)(v16 + 24);
    HIDWORD(v17) |= 1u;
    *((_QWORD *)&v16 + 1) = v12;
    v19[0] = &v15;
    v19[1] = 48;
    ActivityIdCallbackData = FltGetActivityIdCallbackData(a1, &v18);
    v14 = &v18;
    if ( ActivityIdCallbackData < 0 )
      v14 = 0;
    return v5(*(_QWORD *)(a1 + 8), v19, 1, 0x4000000, v9, v14);
  }
  return result;
}

```

## disassembly

```asm
0x140002708  mov     [rsp-8+arg_8], rbx
0x14000270d  mov     [rsp-8+arg_10], rsi
0x140002712  push    rbp
0x140002713  push    rdi
0x140002714  push    r14
0x140002716  lea     rbp, [rsp-47h]
0x14000271b  sub     rsp, 0A0h
0x140002722  mov     rax, cs:__security_cookie
0x140002729  xor     rax, rsp
0x14000272c  mov     [rbp+57h+var_20], rax
0x140002730  mov     rax, cs:qword_140009A00
0x140002737  xorps   xmm0, xmm0
0x14000273a  movups  [rbp+57h+var_70], xmm0
0x14000273e  mov     r14, rdx
0x140002741  mov     rdi, rcx
0x140002744  movups  [rbp+57h+var_60], xmm0
0x140002748  movups  [rbp+57h+var_50], xmm0
0x14000274c  movups  [rbp+57h+var_40], xmm0
0x140002750  mov     rsi, [rax+10h]
0x140002754  test    rsi, rsi
0x140002757  jz      loc_140002840
0x14000275d  mov     rcx, [rcx+10h]
0x140002761  movups  [rbp+57h+var_70], xmm0
0x140002765  movups  [rbp+57h+var_60], xmm0
0x140002769  movups  [rbp+57h+var_50], xmm0
0x14000276d  movzx   r8d, byte ptr [rcx+4]
0x140002772  mov     edx, r8d
0x140002775  sub     edx, 3
0x140002778  jz      loc_140002882
0x14000277e  sub     edx, 1
0x140002781  jz      loc_140002882
0x140002787  sub     edx, 0EAh
0x14000278d  jnz     loc_140002865
0x140002793  mov     rax, [rcx+18h]
0x140002797  mov     qword ptr [rbp+57h+var_70], rax
0x14000279b  mov     rdx, [rcx+20h]
0x14000279f  test    rdx, rdx
0x1400027a2  jz      short loc_1400027B4
0x1400027a4  xor     ecx, ecx
0x1400027a6  add     ecx, [rdx+28h]
0x1400027a9  mov     dword ptr [rbp+57h+var_50+4], ecx
0x1400027ac  mov     rdx, [rdx]
0x1400027af  test    rdx, rdx
0x1400027b2  jnz     short loc_1400027A6
0x1400027b4  mov     ebx, 444h
0x1400027b9  mov     rcx, [rdi+8]; Thread
0x1400027bd  mov     qword ptr [rbp+57h+var_70+8], rdi
0x1400027c1  test    rcx, rcx
0x1400027c4  jz      loc_1400028B9
0x1400027ca  call    cs:__imp_PsGetThreadId
0x1400027d1  nop     dword ptr [rax+rax+00h]
0x1400027d6  mov     dword ptr [rbp+57h+var_50], eax
0x1400027d9  lea     rdx, [rbp+57h+var_40]
0x1400027dd  mov     rax, [r14+20h]
0x1400027e1  mov     rcx, rdi
0x1400027e4  mov     qword ptr [rbp+57h+var_60], rax
0x1400027e8  mov     rax, [rax+18h]
0x1400027ec  or      dword ptr [rbp+57h+var_50+0Ch], 1
0x1400027f0  mov     qword ptr [rbp+57h+var_60+8], rax
0x1400027f4  lea     rax, [rbp+57h+var_70]
0x1400027f8  mov     [rbp+57h+var_30], rax
0x1400027fc  mov     [rbp+57h+var_28], 30h ; '0'
0x140002804  call    cs:__imp_FltGetActivityIdCallbackData
0x14000280b  nop     dword ptr [rax+rax+00h]
0x140002810  xor     ecx, ecx
0x140002812  lea     rdx, [rbp+57h+var_40]
0x140002816  test    eax, eax
0x140002818  mov     r9d, 4000000h
0x14000281e  mov     rax, rsi
0x140002821  cmovs   rdx, rcx
0x140002825  mov     [rsp+0B0h+var_88], rdx
0x14000282a  lea     r8d, [rcx+1]
0x14000282e  mov     rcx, [rdi+8]
0x140002832  lea     rdx, [rbp+57h+var_30]
0x140002836  mov     [rsp+0B0h+var_90], bx
0x14000283b  call    _guard_dispatch_icall
0x140002840  mov     rcx, [rbp+57h+var_20]
0x140002844  xor     rcx, rsp; StackCookie
0x140002847  call    __security_check_cookie
0x14000284c  lea     r11, [rsp+0B0h+var_10]
0x140002854  mov     rbx, [r11+28h]
0x140002858  mov     rsi, [r11+30h]
0x14000285c  mov     rsp, r11
0x14000285f  pop     r14
0x140002861  pop     rdi
0x140002862  pop     rbp
0x140002863  retn
0x140002865  cmp     edx, 3
0x140002868  jnz     short loc_140002840
0x14000286a  mov     rax, [rcx+18h]
0x14000286e  mov     ebx, 443h
0x140002873  mov     qword ptr [rbp+57h+var_70], rax
0x140002877  mov     eax, [rcx+20h]
0x14000287a  mov     dword ptr [rbp+57h+var_50+4], eax
0x14000287d  jmp     loc_1400027B9
0x140002882  mov     al, [rcx+5]
0x140002885  and     al, 4
0x140002887  cmp     r8b, 3
0x14000288b  jnz     short loc_1400028AE
0x14000288d  test    al, al
0x14000288f  jnz     short loc_140002840
0x140002891  mov     ebx, 443h
0x140002896  mov     rax, [rcx+28h]
0x14000289a  mov     qword ptr [rbp+57h+var_70], rax
0x14000289e  mov     eax, [rcx+18h]
0x1400028a1  mov     dword ptr [rbp+57h+var_50+4], eax
0x1400028a4  mov     eax, [rcx]
0x1400028a6  mov     dword ptr [rbp+57h+var_50+8], eax
0x1400028a9  jmp     loc_1400027B9
0x1400028ae  test    al, al
0x1400028b0  jz      short loc_140002840
0x1400028b2  mov     ebx, 444h
0x1400028b7  jmp     short loc_140002896
0x1400028b9  or      eax, 0FFFFFFFFh
0x1400028bc  jmp     loc_1400027D6
```
