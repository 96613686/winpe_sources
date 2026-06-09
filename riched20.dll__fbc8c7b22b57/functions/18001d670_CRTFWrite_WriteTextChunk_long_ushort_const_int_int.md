# CRTFWrite::WriteTextChunk(long,ushort const *,int,int)

- ea: `0x18001d670`
- end: `0x18001dade`
- name: `?WriteTextChunk@CRTFWrite@@AEAAHJPEBGHH@Z`
- size: `1134`
- prototype: `__int64 __fastcall(CRTFWrite *__hidden this, int, const unsigned __int16 *, UINT CodePage, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001d414`

## callees

- `0x18001d3c8`
- `0x18001d670`
- `0x18001dae4`
- `0x18001dfe0`
- `0x18001e170`
- `0x18004223c`
- `0x1800466f0`
- `0x18004710c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18001da3d`
- `KERNEL32!GetProcessHeap` at `0x18001da3d`
- `KERNEL32!HeapAlloc` at `0x18001d6e3`
- `KERNEL32!HeapAlloc` at `0x18001d6e3`

## pseudocode

```c
__int64 __fastcall CRTFWrite::WriteTextChunk(
        CRTFWrite *this,
        unsigned int a2,
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
  BOOL v32; // [rsp+B8h] [rbp+20h] BYREF

  v31 = a2;
  v29[0] = 0;
  v6 = 63;
  v30 = 0;
  if ( CodePage != 65001 )
    v6 = 0;
  v7 = 12288;
  v8 = (CHAR *)*((_QWORD *)this + 20);
  LOBYTE(v32) = v6;
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
    v14 = CW32System::WCTMB(0xFFFFFFFF, a2, a3, a2, v8, v7, 0, 0, 0, 0);
  }
  else
  {
    v14 = CW32System::WCTMB(CodePage, a2, a3, a2, v8, v7, (BOOL)&v32, &v30, v29, 0);
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
        else if ( (unsigned __int8)v20 == v32 && v23 )
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
0x18001d670  mov     rax, rsp
0x18001d673  mov     [rax+10h], edx
0x18001d676  push    rbx
0x18001d677  push    rbp
0x18001d678  push    rsi
0x18001d679  push    rdi
0x18001d67a  push    r13
0x18001d67c  push    r14
0x18001d67e  push    r15
0x18001d680  sub     rsp, 60h
0x18001d684  xor     r13d, r13d
0x18001d687  mov     rbx, rcx
0x18001d68a  cmp     r9d, 0FDE9h
0x18001d691  mov     [rax-48h], r13d
0x18001d695  mov     ecx, 3Fh ; '?'
0x18001d69a  mov     [rax+8], r13d
0x18001d69e  cmovnz  ecx, r13d
0x18001d6a2  mov     esi, 3000h
0x18001d6a7  mov     rdi, [rbx+0A0h]
0x18001d6ae  mov     r15d, r9d
0x18001d6b1  mov     [rax+20h], cl
0x18001d6b4  mov     r14, r8
0x18001d6b7  mov     eax, 5000h
0x18001d6bc  mov     ebp, r13d
0x18001d6bf  cmovnz  esi, eax
0x18001d6c2  test    rdi, rdi
0x18001d6c5  jnz     loc_18001D9B2
0x18001d6cb  mov     rax, cs:?g_hHeap@@3PEAXEA; void * g_hHeap
0x18001d6d2  test    rax, rax
0x18001d6d5  jz      loc_18001DA3D
0x18001d6db  mov     r8d, esi; dwBytes
0x18001d6de  xor     edx, edx; dwFlags
0x18001d6e0  mov     rcx, rax; hHeap
0x18001d6e3  call    cs:__imp_HeapAlloc
0x18001d6ea  nop     dword ptr [rax+rax+00h]
0x18001d6ef  mov     [rbx+0A0h], rax
0x18001d6f6  mov     rdi, rax
0x18001d6f9  test    rax, rax
0x18001d6fc  jnz     loc_18001DA65
0x18001d702  mov     rcx, [rbx+38h]
0x18001d706  mov     rcx, [rcx+90h]; this
0x18001d70d  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18001d712  mov     dword ptr [rbx+30h], 9
0x18001d719  jmp     loc_18001D81C
0x18001d71e  mov     [rsp+98h+var_58], r13; int *
0x18001d723  mov     ecx, 0FFFFFFFFh; CodePage
0x18001d728  mov     [rsp+98h+var_60], r13; int *
0x18001d72d  mov     qword ptr [rsp+98h+UsedDefaultChar], r13; UsedDefaultChar
0x18001d732  mov     [rsp+98h+var_70], esi; int
0x18001d736  mov     [rsp+98h+var_78], rdi; LPSTR
0x18001d73b  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x18001d740  mov     r12d, [rsp+98h+arg_8]
0x18001d748  mov     esi, eax
0x18001d74a  mov     r10d, [rsp+98h+arg_20]
0x18001d752  cmp     eax, r12d
0x18001d755  jle     loc_18001DA71
0x18001d75b  mov     ecx, 1
0x18001d760  mov     [rsp+98h+var_48], ecx
0x18001d764  cmp     [rbx+30h], r13d
0x18001d768  jnz     loc_18001D814
0x18001d76e  mov     rdx, 280000001h
0x18001d778  test    esi, esi
0x18001d77a  jle     loc_18001D814
0x18001d780  movzx   ebp, byte ptr [rdi]
0x18001d783  dec     esi
0x18001d785  lea     eax, [rbp-20h]
0x18001d788  cmp     eax, 5Ah ; 'Z'
0x18001d78b  ja      loc_18001D863
0x18001d791  cmp     r15d, 0FDE9h
0x18001d798  jz      loc_18001D82F
0x18001d79e  movzx   r13d, word ptr [r14]
0x18001d7a2  test    ecx, ecx
0x18001d7a4  jnz     loc_18001D98B
0x18001d7aa  mov     r12d, 1
0x18001d7b0  cmp     r13d, 80h
0x18001d7b7  jnb     loc_18001D8A1
0x18001d7bd  mov     ecx, [rsp+98h+arg_0]
0x18001d7c4  cmp     r12d, 2
0x18001d7c8  jz      loc_18001D95A
0x18001d7ce  movsx   eax, byte ptr [rsp+98h+arg_18]
0x18001d7d6  movzx   r8d, bpl
0x18001d7da  cmp     r8d, eax
0x18001d7dd  jz      loc_18001DA8A
0x18001d7e3  lea     eax, [r8-20h]
0x18001d7e7  cmp     eax, 5Fh ; '_'
0x18001d7ea  ja      loc_18001DA10
0x18001d7f0  movzx   edx, bpl; char
0x18001d7f4  mov     rcx, rbx; this
0x18001d7f7  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18001d7fc  dec     [rsp+98h+arg_8]
0x18001d803  inc     rdi
0x18001d806  add     r14, 2
0x18001d80a  cmp     dword ptr [rbx+30h], 0
0x18001d80e  jz      loc_18001DA24
0x18001d814  mov     r12, [rsp+98h+arg_10]
0x18001d81c  mov     eax, [rbx+30h]
0x18001d81f  add     rsp, 60h
0x18001d823  pop     r15
0x18001d825  pop     r14
0x18001d827  pop     r13
0x18001d829  pop     rdi
0x18001d82a  pop     rsi
0x18001d82b  pop     rbp
0x18001d82c  pop     rbx
0x18001d82d  retn
0x18001d82f  movzx   edx, bpl; char
0x18001d833  mov     rcx, rbx; this
0x18001d836  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18001d83b  cmp     bpl, 0C0h
0x18001d83f  jb      short loc_18001D7FC
0x18001d841  movzx   edx, byte ptr [rdi+1]; char
0x18001d845  inc     rdi
0x18001d848  mov     rcx, rbx; this
0x18001d84b  dec     esi
0x18001d84d  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18001d852  cmp     bpl, 0E0h
0x18001d856  jb      short loc_18001D7FC
0x18001d858  movzx   edx, byte ptr [rdi+1]
0x18001d85c  inc     rdi
0x18001d85f  dec     esi
0x18001d861  jmp     short loc_18001D7F4
0x18001d863  movsx   eax, bpl
0x18001d867  sub     eax, 9
0x18001d86a  cmp     bpl, 9
0x18001d86e  jnz     loc_18001D933
0x18001d874  xor     r9d, r9d; int
0x18001d877  mov     r8d, esi; int
0x18001d87a  mov     rdx, rdi; void *
0x18001d87d  mov     rcx, rbx; this
0x18001d880  call    ?MapToRTFKeyword@CRTFWrite@@AEAAHPEAXHH@Z; CRTFWrite::MapToRTFKeyword(void *,int,int)
0x18001d885  movsxd  rcx, eax
0x18001d888  sub     esi, eax
0x18001d88a  add     rdi, rcx
0x18001d88d  sub     r12d, eax
0x18001d890  mov     [rsp+98h+arg_8], r12d
0x18001d898  lea     r14, [r14+rcx*2]
0x18001d89c  jmp     loc_18001D7FC
0x18001d8a1  test    r10d, r10d
0x18001d8a4  jnz     loc_18001D7BD
0x18001d8aa  cmp     [rbx+92h], r10b
0x18001d8b1  jz      loc_18001D7BD
0x18001d8b7  cmp     r15d, 2Ah ; '*'
0x18001d8bb  jz      loc_18001D7BD
0x18001d8c1  cmp     r12d, [rbx+88h]
0x18001d8c8  jz      short loc_18001D8EF
0x18001d8ca  mov     r9d, r12d; int
0x18001d8cd  mov     [rbx+88h], r12d
0x18001d8d4  mov     edx, 1; int
0x18001d8d9  mov     r8d, 0ECh; int
0x18001d8df  mov     rcx, rbx; this
0x18001d8e2  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001d8e7  test    eax, eax
0x18001d8e9  jz      loc_18001D814
0x18001d8ef  mov     r9d, r13d; int
0x18001d8f2  mov     edx, 1; int
0x18001d8f7  mov     r8d, 0EBh; int
0x18001d8fd  mov     rcx, rbx; this
0x18001d900  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001d905  test    eax, eax
0x18001d907  jz      loc_18001D814
0x18001d90d  mov     ecx, [rsp+98h+arg_0]
0x18001d914  mov     r10d, [rsp+98h+arg_20]
0x18001d91c  test    ecx, ecx
0x18001d91e  jz      loc_18001D7C4
0x18001d924  mov     bpl, 3Fh ; '?'
0x18001d927  mov     byte ptr [rbx+8Eh], 0
0x18001d92e  jmp     loc_18001D7C4
0x18001d933  cmp     eax, 4
0x18001d936  jbe     loc_18001D874
0x18001d93c  lea     eax, [rbp-5Ch]
0x18001d93f  cmp     al, 21h ; '!'
0x18001d941  ja      loc_18001D791
0x18001d947  movsx   rax, al
0x18001d94b  bt      rdx, rax
0x18001d94f  jnb     loc_18001D791
0x18001d955  jmp     loc_18001D874
0x18001d95a  inc     rdi
0x18001d95d  dec     esi
0x18001d95f  test    r10d, r10d
0x18001d962  jz      short loc_18001D96F
0x18001d964  add     r14, 2
0x18001d968  dec     [rsp+98h+arg_8]
0x18001d96f  movzx   r9d, byte ptr [rdi]
0x18001d973  lea     rdx, a02x02x; "\\'%02x\\'%02x"
0x18001d97a  movzx   r8d, bpl
0x18001d97e  mov     rcx, rbx; this
0x18001d981  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18001d986  jmp     loc_18001D7FC
0x18001d98b  test    esi, esi
0x18001d98d  jz      loc_18001D7AA
0x18001d993  mov     edx, r15d; unsigned int
0x18001d996  movzx   ecx, bpl; unsigned __int8
0x18001d99a  call    ?GetTrailBytesCount@CW32System@@SAHEI@Z; CW32System::GetTrailBytesCount(uchar,uint)
0x18001d99f  test    eax, eax
0x18001d9a1  jz      loc_18001D7AA
0x18001d9a7  mov     r12d, 2
0x18001d9ad  jmp     loc_18001D7B0
0x18001d9b2  mov     r9d, edx; int
0x18001d9b5  mov     [rsp+98h+arg_10], r12
0x18001d9bd  mov     r8, r14; unsigned __int16 *
0x18001d9c0  mov     [rsp+98h+var_50], r13d; int
0x18001d9c5  cmp     [rsp+98h+arg_20], ebp
0x18001d9cc  jnz     loc_18001D71E
0x18001d9d2  lea     rax, [rsp+98h+var_48]
0x18001d9d7  mov     ecx, r15d; CodePage
0x18001d9da  mov     [rsp+98h+var_58], rax; int *
0x18001d9df  lea     rax, [rsp+98h+arg_0]
0x18001d9e7  mov     [rsp+98h+var_60], rax; int *
0x18001d9ec  lea     rax, [rsp+98h+arg_18]
0x18001d9f4  mov     qword ptr [rsp+98h+UsedDefaultChar], rax; UsedDefaultChar
0x18001d9f9  mov     [rsp+98h+var_70], esi; int
0x18001d9fd  mov     [rsp+98h+var_78], rdi; LPSTR
0x18001da02  call    ?WCTMB@CW32System@@SAHHKPEBGHPEADHPEBDPEAH3H@Z; CW32System::WCTMB(int,ulong,ushort const *,int,char *,int,char const *,int *,int *,int)
0x18001da07  mov     ebp, [rsp+98h+var_48]
0x18001da0b  jmp     loc_18001D740
0x18001da10  lea     rdx, a02x02x+6; Format
0x18001da17  mov     rcx, rbx; this
0x18001da1a  call    ?printF@CRTFWrite@@AEAAHPEBDZZ; CRTFWrite::printF(char const *,...)
0x18001da1f  jmp     loc_18001D7FC
0x18001da24  mov     r12d, [rsp+98h+arg_8]
0x18001da2c  mov     ecx, [rsp+98h+var_48]
0x18001da30  mov     r10d, [rsp+98h+arg_20]
0x18001da38  jmp     loc_18001D76E
0x18001da3d  call    cs:__imp_GetProcessHeap
0x18001da44  nop     dword ptr [rax+rax+00h]
0x18001da49  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x18001da50  test    rax, rax
0x18001da53  jnz     loc_18001D6DB
0x18001da59  mov     [rbx+0A0h], r13
0x18001da60  jmp     loc_18001D702
0x18001da65  mov     edx, [rsp+98h+arg_8]
0x18001da6c  jmp     loc_18001D9B2
0x18001da71  test    r10d, r10d
0x18001da74  jnz     loc_18001D75B
0x18001da7a  mov     ecx, r13d
0x18001da7d  test    ebp, ebp
0x18001da7f  jz      loc_18001D760
0x18001da85  jmp     loc_18001D75B
0x18001da8a  test    ecx, ecx
0x18001da8c  jz      loc_18001D7E3
0x18001da92  mov     eax, [rsp+98h+arg_8]
0x18001da99  mov     r9d, 3Fh ; '?'
0x18001da9f  test    eax, eax
0x18001daa1  mov     edx, 1; int
0x18001daa6  mov     r8d, 0EBh; int
0x18001daac  mov     rcx, rbx; this
0x18001daaf  cmovg   r9d, r13d; int
0x18001dab3  call    ?PutCtrlWord@CRTFWrite@@AEAAHJJJ@Z; CRTFWrite::PutCtrlWord(long,long,long)
0x18001dab8  test    eax, eax
0x18001daba  jz      loc_18001D814
0x18001dac0  mov     dl, 3Fh ; '?'; char
0x18001dac2  mov     byte ptr [rbx+8Eh], 0
0x18001dac9  mov     rcx, rbx; this
0x18001dacc  call    ?PutChar@CRTFWrite@@AEAAHD@Z; CRTFWrite::PutChar(char)
0x18001dad1  test    eax, eax
0x18001dad3  jz      loc_18001D814
0x18001dad9  jmp     loc_18001D7FC
```
