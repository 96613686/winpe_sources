# CRTFWrite::WriteTextChunk(long,ushort const *,int,int)

- ea: `0x1800290e0`
- end: `0x180029541`
- name: `?WriteTextChunk@CRTFWrite@@AEAAHJPEBGHH@Z`
- size: `1121`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, int, const unsigned __int16 *, UINT CodePage, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180028e88`

## callees

- `0x180028e40`
- `0x1800290e0`
- `0x180029548`
- `0x180029a40`
- `0x180029bd0`
- `0x18002a424`
- `0x1800455c4`
- `0x18004609c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800294a6`
- `KERNEL32!GetProcessHeap` at `0x1800294a6`
- `KERNEL32!HeapAlloc` at `0x180029153`
- `KERNEL32!HeapAlloc` at `0x180029153`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteTextChunk(
        CRTFWrite *this,
        int a2,
        const unsigned __int16 *a3,
        UINT CodePage,
        int a5)
{
  char v6; // cl
  unsigned int v7; // esi
  CHAR *v8; // rdi
  int v11; // ebp
  HANDLE ProcessHeap; // rax
  CHAR *v13; // rax
  int v14; // eax
  int v15; // r12d
  int v16; // esi
  int v17; // r10d
  int v18; // ecx
  __int64 v19; // rdx
  int v20; // ebp
  unsigned int v21; // r13d
  int v22; // r12d
  int v23; // ecx
  char v24; // dl
  char v26; // dl
  int v27; // eax
  int v28; // r9d
  int v29[18]; // [rsp+50h] [rbp-48h] BYREF
  int v30; // [rsp+A0h] [rbp+8h] BYREF
  int v31; // [rsp+A8h] [rbp+10h]
  BOOL UsedDefaultChar; // [rsp+B8h] [rbp+20h] BYREF

  v31 = a2;
  v29[0] = 0;
  v6 = 63;
  v30 = 0;
  if ( CodePage != 65001 )
    v6 = 0;
  v7 = 12288;
  v8 = (CHAR *)*((_QWORD *)this + 20);
  LOBYTE(UsedDefaultChar) = v6;
  v11 = 0;
  if ( CodePage != 65001 )
    v7 = 20480;
  if ( !v8 )
  {
    ProcessHeap = g_hHeap;
    if ( !g_hHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hHeap = ProcessHeap;
      if ( !ProcessHeap )
      {
        *((_QWORD *)this + 20) = 0;
        goto LABEL_8;
      }
    }
    v13 = (CHAR *)HeapAlloc(ProcessHeap, 0, v7);
    *((_QWORD *)this + 20) = v13;
    v8 = v13;
    if ( !v13 )
    {
LABEL_8:
      CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 7) + 144LL));
      *((_DWORD *)this + 12) = 9;
      return *((unsigned int *)this + 12);
    }
    a2 = v31;
  }
  if ( a5 )
  {
    v14 = CW32System::WCTMB(-1, a2, a3, a2, v8, v7, 0, 0, 0, 0);
  }
  else
  {
    v14 = CW32System::WCTMB(CodePage, a2, a3, a2, v8, v7, (CHAR *)&UsedDefaultChar, &v30, v29, 0);
    v11 = v29[0];
  }
  v15 = v31;
  v16 = v14;
  v17 = a5;
  if ( v14 > v31 || a5 || (v18 = 0, v11) )
    v18 = 1;
  v29[0] = v18;
  if ( !*((_DWORD *)this + 12) )
  {
    while ( 1 )
    {
      v19 = 0x280000001LL;
      if ( v16 <= 0 )
        return *((unsigned int *)this + 12);
      v20 = (unsigned __int8)*v8;
      --v16;
      if ( (unsigned int)(v20 - 32) > 0x5A
        && ((_BYTE)v20 == 9
         || (unsigned int)((char)v20 - 9) <= 4
         || (unsigned __int8)(v20 - 92) <= 0x21u && _bittest64(&v19, (char)(v20 - 92))) )
      {
        v27 = CRTFWrite::MapToRTFKeyword(this, v8, v16, 0);
        v16 -= v27;
        v8 += v27;
        v31 = v15 - v27;
        a3 += v27;
      }
      else if ( CodePage == 65001 )
      {
        CRTFWrite::PutChar(this, v20);
        if ( (unsigned __int8)v20 >= 0xC0u )
        {
          v26 = *++v8;
          --v16;
          CRTFWrite::PutChar(this, v26);
          if ( (unsigned __int8)v20 >= 0xE0u )
          {
            v24 = *++v8;
            --v16;
            goto LABEL_24;
          }
        }
      }
      else
      {
        v21 = *a3;
        if ( v18 && v16 && (unsigned int)CW32System::GetTrailBytesCount(v20, CodePage) )
          v22 = 2;
        else
          v22 = 1;
        if ( v21 < 0x80 || v17 || !*((_BYTE *)this + 146) || CodePage == 42 )
        {
          v23 = v30;
        }
        else
        {
          if ( v22 != *((_DWORD *)this + 34) )
          {
            *((_DWORD *)this + 34) = v22;
            if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 1, 236, v22) )
              return *((unsigned int *)this + 12);
          }
          if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 1, 235, v21) )
            return *((unsigned int *)this + 12);
          v23 = v30;
          v17 = a5;
          if ( v30 )
          {
            LOBYTE(v20) = 63;
            *((_BYTE *)this + 142) = 0;
          }
        }
        if ( v22 == 2 )
        {
          ++v8;
          --v16;
          if ( v17 )
          {
            ++a3;
            --v31;
          }
          CRTFWrite::printF(this, "\\'%02x\\'%02x", (unsigned __int8)v20, (unsigned __int8)*v8);
        }
        else if ( (unsigned __int8)v20 == UsedDefaultChar && v23 )
        {
          v28 = 63;
          if ( v31 > 0 )
            v28 = v21;
          if ( !(unsigned int)CRTFWrite::PutCtrlWord(this, 1, 235, v28) )
            return *((unsigned int *)this + 12);
          *((_BYTE *)this + 142) = 0;
          if ( !(unsigned int)CRTFWrite::PutChar(this, 63) )
            return *((unsigned int *)this + 12);
        }
        else
        {
          if ( (unsigned int)(unsigned __int8)v20 - 32 <= 0x5F )
          {
            v24 = v20;
LABEL_24:
            CRTFWrite::PutChar(this, v24);
            goto LABEL_25;
          }
          CRTFWrite::printF(this, "\\'%02x", (unsigned __int8)v20);
        }
      }
LABEL_25:
      --v31;
      ++v8;
      ++a3;
      if ( *((_DWORD *)this + 12) )
        return *((unsigned int *)this + 12);
      v15 = v31;
      v18 = v29[0];
      v17 = a5;
    }
  }
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x1800290e0  mov     rax, rsp
0x1800290e3  mov     [rax+10h], edx
0x1800290e6  push    rbx
0x1800290e7  push    rbp
0x1800290e8  push    rsi
0x1800290e9  push    rdi
0x1800290ea  push    r13
0x1800290ec  push    r14
0x1800290ee  push    r15
0x1800290f0  sub     rsp, 60h
0x1800290f4  xor     r13d, r13d
0x1800290f7  mov     rbx, rcx
0x1800290fa  cmp     r9d, 0FDE9h
0x180029101  mov     [rax-48h], r13d
0x180029105  mov     ecx, 3Fh ; '?'
0x18002910a  mov     [rax+8], r13d
0x18002910e  cmovnz  ecx, r13d
0x180029112  mov     esi, 3000h
0x180029117  mov     rdi, [rbx+0A0h]
0x18002911e  mov     r15d, r9d
0x180029121  mov     [rax+20h], cl
0x180029124  mov     r14, r8
0x180029127  mov     eax, 5000h
0x18002912c  mov     ebp, r13d
0x18002912f  cmovnz  esi, eax
0x180029132  test    rdi, rdi
0x180029135  jnz     loc_18002941B
0x18002913b  mov     rax, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x180029142  test    rax, rax
0x180029145  jz      loc_1800294A6
0x18002914b  mov     r8d, esi; dwBytes
0x18002914e  xor     edx, edx; dwFlags
0x180029150  mov     rcx, rax; hHeap
0x180029153  call    cs:__imp_HeapAlloc
0x180029159  mov     [rbx+0A0h], rax
0x180029160  mov     rdi, rax
0x180029163  test    rax, rax
0x180029166  jnz     loc_1800294C8
0x18002916c  mov     rcx, [rbx+38h]
0x180029170  mov     rcx, [rcx+90h]; this
0x180029177  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18002917c  mov     dword ptr [rbx+30h], 9
0x180029183  jmp     loc_180029286
0x180029188  mov     [rsp+98h+var_58], r13; int *
0x18002918d  mov     ecx, 0FFFFFFFFh; CodePage
0x180029192  mov     [rsp+98h+var_60], r13; int *
0x180029197  mov     qword ptr [rsp+98h+UsedDefaultChar], r13; UsedDefaultChar
0x18002919c  mov     [rsp+98h+var_70], esi; int
0x1800291a0  mov     [rsp+98h+var_78], rdi; LPSTR
0x1800291a5  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x1800291aa  mov     r12d, [rsp+98h+arg_8]
0x1800291b2  mov     esi, eax
0x1800291b4  mov     r10d, [rsp+98h+arg_20]
0x1800291bc  cmp     eax, r12d
0x1800291bf  jle     loc_1800294D4
0x1800291c5  mov     ecx, 1
0x1800291ca  mov     [rsp+98h+var_48], ecx
0x1800291ce  cmp     [rbx+30h], r13d
0x1800291d2  jnz     loc_18002927E
0x1800291d8  mov     rdx, 280000001h
0x1800291e2  test    esi, esi
0x1800291e4  jle     loc_18002927E
0x1800291ea  movzx   ebp, byte ptr [rdi]
0x1800291ed  dec     esi
0x1800291ef  lea     eax, [rbp-20h]
0x1800291f2  cmp     eax, 5Ah ; 'Z'
0x1800291f5  ja      loc_1800292CC
0x1800291fb  cmp     r15d, 0FDE9h
0x180029202  jz      loc_180029298
0x180029208  movzx   r13d, word ptr [r14]
0x18002920c  test    ecx, ecx
0x18002920e  jnz     loc_1800293F4
0x180029214  mov     r12d, 1
0x18002921a  cmp     r13d, 80h
0x180029221  jnb     loc_18002930A
0x180029227  mov     ecx, [rsp+98h+arg_0]
0x18002922e  cmp     r12d, 2
0x180029232  jz      loc_1800293C3
0x180029238  movsx   eax, byte ptr [rsp+98h+arg_18]
0x180029240  movzx   r8d, bpl
0x180029244  cmp     r8d, eax
0x180029247  jz      loc_1800294ED
0x18002924d  lea     eax, [r8-20h]
0x180029251  cmp     eax, 5Fh ; '_'
0x180029254  ja      loc_180029479
0x18002925a  movzx   edx, bpl; char
0x18002925e  mov     rcx, rbx; this
0x180029261  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180029266  dec     [rsp+98h+arg_8]
0x18002926d  inc     rdi
0x180029270  add     r14, 2
0x180029274  cmp     dword ptr [rbx+30h], 0
0x180029278  jz      loc_18002948D
0x18002927e  mov     r12, [rsp+98h+arg_10]
0x180029286  mov     eax, [rbx+30h]
0x180029289  add     rsp, 60h
0x18002928d  pop     r15
0x18002928f  pop     r14
0x180029291  pop     r13
0x180029293  pop     rdi
0x180029294  pop     rsi
0x180029295  pop     rbp
0x180029296  pop     rbx
0x180029297  retn
0x180029298  movzx   edx, bpl; char
0x18002929c  mov     rcx, rbx; this
0x18002929f  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x1800292a4  cmp     bpl, 0C0h
0x1800292a8  jb      short loc_180029266
0x1800292aa  movzx   edx, byte ptr [rdi+1]; char
0x1800292ae  inc     rdi
0x1800292b1  mov     rcx, rbx; this
0x1800292b4  dec     esi
0x1800292b6  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x1800292bb  cmp     bpl, 0E0h
0x1800292bf  jb      short loc_180029266
0x1800292c1  movzx   edx, byte ptr [rdi+1]
0x1800292c5  inc     rdi
0x1800292c8  dec     esi
0x1800292ca  jmp     short loc_18002925E
0x1800292cc  movsx   eax, bpl
0x1800292d0  sub     eax, 9
0x1800292d3  cmp     bpl, 9
0x1800292d7  jnz     loc_18002939C
0x1800292dd  xor     r9d, r9d; int
0x1800292e0  mov     r8d, esi; int
0x1800292e3  mov     rdx, rdi; void *
0x1800292e6  mov     rcx, rbx; this
0x1800292e9  call    ?MapToRTFKeyword@CRTFWrite@@AEAAHPEAXHH@Z; CRTFWrite::MapToRTFKeyword(void *,int,int)
0x1800292ee  movsxd  rcx, eax
0x1800292f1  sub     esi, eax
0x1800292f3  add     rdi, rcx
0x1800292f6  sub     r12d, eax
0x1800292f9  mov     [rsp+98h+arg_8], r12d
0x180029301  lea     r14, [r14+rcx*2]
0x180029305  jmp     loc_180029266
0x18002930a  test    r10d, r10d
0x18002930d  jnz     loc_180029227
0x180029313  cmp     [rbx+92h], r10b
0x18002931a  jz      loc_180029227
0x180029320  cmp     r15d, 2Ah ; '*'
0x180029324  jz      loc_180029227
0x18002932a  cmp     r12d, [rbx+88h]
0x180029331  jz      short loc_180029358
0x180029333  mov     r9d, r12d; int
0x180029336  mov     [rbx+88h], r12d
0x18002933d  mov     edx, 1; int
0x180029342  mov     r8d, 0ECh; int
0x180029348  mov     rcx, rbx; this
0x18002934b  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x180029350  test    eax, eax
0x180029352  jz      loc_18002927E
0x180029358  mov     r9d, r13d; int
0x18002935b  mov     edx, 1; int
0x180029360  mov     r8d, 0EBh; int
0x180029366  mov     rcx, rbx; this
0x180029369  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18002936e  test    eax, eax
0x180029370  jz      loc_18002927E
0x180029376  mov     ecx, [rsp+98h+arg_0]
0x18002937d  mov     r10d, [rsp+98h+arg_20]
0x180029385  test    ecx, ecx
0x180029387  jz      loc_18002922E
0x18002938d  mov     bpl, 3Fh ; '?'
0x180029390  mov     byte ptr [rbx+8Eh], 0
0x180029397  jmp     loc_18002922E
0x18002939c  cmp     eax, 4
0x18002939f  jbe     loc_1800292DD
0x1800293a5  lea     eax, [rbp-5Ch]
0x1800293a8  cmp     al, 21h ; '!'
0x1800293aa  ja      loc_1800291FB
0x1800293b0  movsx   rax, al
0x1800293b4  bt      rdx, rax
0x1800293b8  jnb     loc_1800291FB
0x1800293be  jmp     loc_1800292DD
0x1800293c3  inc     rdi
0x1800293c6  dec     esi
0x1800293c8  test    r10d, r10d
0x1800293cb  jz      short loc_1800293D8
0x1800293cd  add     r14, 2
0x1800293d1  dec     [rsp+98h+arg_8]
0x1800293d8  movzx   r9d, byte ptr [rdi]
0x1800293dc  lea     rdx, a02x02x; "\\'%02x\\'%02x"
0x1800293e3  movzx   r8d, bpl
0x1800293e7  mov     rcx, rbx; this
0x1800293ea  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x1800293ef  jmp     loc_180029266
0x1800293f4  test    esi, esi
0x1800293f6  jz      loc_180029214
0x1800293fc  mov     edx, r15d; unsigned int
0x1800293ff  movzx   ecx, bpl; unsigned __int8
0x180029403  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x180029408  test    eax, eax
0x18002940a  jz      loc_180029214
0x180029410  mov     r12d, 2
0x180029416  jmp     loc_18002921A
0x18002941b  mov     r9d, edx; int
0x18002941e  mov     [rsp+98h+arg_10], r12
0x180029426  mov     r8, r14; unsigned __int16 *
0x180029429  mov     [rsp+98h+var_50], r13d; int
0x18002942e  cmp     [rsp+98h+arg_20], ebp
0x180029435  jnz     loc_180029188
0x18002943b  lea     rax, [rsp+98h+var_48]
0x180029440  mov     ecx, r15d; CodePage
0x180029443  mov     [rsp+98h+var_58], rax; int *
0x180029448  lea     rax, [rsp+98h+arg_0]
0x180029450  mov     [rsp+98h+var_60], rax; int *
0x180029455  lea     rax, [rsp+98h+arg_18]
0x18002945d  mov     qword ptr [rsp+98h+UsedDefaultChar], rax; UsedDefaultChar
0x180029462  mov     [rsp+98h+var_70], esi; int
0x180029466  mov     [rsp+98h+var_78], rdi; LPSTR
0x18002946b  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x180029470  mov     ebp, [rsp+98h+var_48]
0x180029474  jmp     loc_1800291AA
0x180029479  lea     rdx, a02x02x+6; Format
0x180029480  mov     rcx, rbx; this
0x180029483  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x180029488  jmp     loc_180029266
0x18002948d  mov     r12d, [rsp+98h+arg_8]
0x180029495  mov     ecx, [rsp+98h+var_48]
0x180029499  mov     r10d, [rsp+98h+arg_20]
0x1800294a1  jmp     loc_1800291D8
0x1800294a6  call    cs:__imp_GetProcessHeap
0x1800294ac  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x1800294b3  test    rax, rax
0x1800294b6  jnz     loc_18002914B
0x1800294bc  mov     [rbx+0A0h], r13
0x1800294c3  jmp     loc_18002916C
0x1800294c8  mov     edx, [rsp+98h+arg_8]
0x1800294cf  jmp     loc_18002941B
0x1800294d4  test    r10d, r10d
0x1800294d7  jnz     loc_1800291C5
0x1800294dd  mov     ecx, r13d
0x1800294e0  test    ebp, ebp
0x1800294e2  jz      loc_1800291CA
0x1800294e8  jmp     loc_1800291C5
0x1800294ed  test    ecx, ecx
0x1800294ef  jz      loc_18002924D
0x1800294f5  mov     eax, [rsp+98h+arg_8]
0x1800294fc  mov     r9d, 3Fh ; '?'
0x180029502  test    eax, eax
0x180029504  mov     edx, 1; int
0x180029509  mov     r8d, 0EBh; int
0x18002950f  mov     rcx, rbx; this
0x180029512  cmovg   r9d, r13d; int
0x180029516  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18002951b  test    eax, eax
0x18002951d  jz      loc_18002927E
0x180029523  mov     dl, 3Fh ; '?'; char
0x180029525  mov     byte ptr [rbx+8Eh], 0
0x18002952c  mov     rcx, rbx; this
0x18002952f  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x180029534  test    eax, eax
0x180029536  jz      loc_18002927E
0x18002953c  jmp     loc_180029266
```
