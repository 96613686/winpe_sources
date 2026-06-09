# CSAMIInterpreter::NewToken(CToken &)

- ea: `0x180124250`
- end: `0x180124b86`
- name: `?NewToken@CSAMIInterpreter@@EEAAJAEAVCToken@@@Z`
- size: `2358`
- prototype: `__int64 __fastcall(CSAMIInterpreter *__hidden this, struct CToken *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800135b0`
- `0x18001a050`
- `0x180038458`
- `0x1800384a4`
- `0x1800742b0`
- `0x1801236fc`
- `0x180123728`
- `0x180123754`
- `0x180124250`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180124744`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180124744`
- `KERNEL32!CompareStringA` at `0x180124574`
- `KERNEL32!CompareStringA` at `0x1801245b9`
- `KERNEL32!CompareStringA` at `0x1801245f1`
- `KERNEL32!CompareStringA` at `0x18012472a`
- `KERNEL32!CompareStringA` at `0x1801249f5`
- `KERNEL32!CompareStringA` at `0x180124af7`
- `KERNEL32!CompareStringA` at `0x180124574`
- `KERNEL32!CompareStringA` at `0x1801245b9`
- `KERNEL32!CompareStringA` at `0x1801245f1`
- `KERNEL32!CompareStringA` at `0x18012472a`
- `KERNEL32!CompareStringA` at `0x1801249f5`
- `KERNEL32!CompareStringA` at `0x180124af7`
- `KERNEL32!lstrlenA` at `0x1801247f9`
- `KERNEL32!lstrlenA` at `0x18012491a`
- `KERNEL32!lstrlenA` at `0x180124964`
- `KERNEL32!lstrlenA` at `0x180124a0c`
- `KERNEL32!lstrlenA` at `0x180124a4a`
- `KERNEL32!lstrlenA` at `0x180124a8d`
- `KERNEL32!lstrlenA` at `0x180124b0e`
- `KERNEL32!lstrlenA` at `0x1801247f9`
- `KERNEL32!lstrlenA` at `0x18012491a`
- `KERNEL32!lstrlenA` at `0x180124964`
- `KERNEL32!lstrlenA` at `0x180124a0c`
- `KERNEL32!lstrlenA` at `0x180124a4a`
- `KERNEL32!lstrlenA` at `0x180124a8d`
- `KERNEL32!lstrlenA` at `0x180124b0e`
- `KERNEL32!lstrcmpA` at `0x180124668`
- `KERNEL32!lstrcmpA` at `0x180124668`

## pseudocode

```c
__int64 __fastcall CSAMIInterpreter::NewToken(CSAMIInterpreter *this, struct CToken *a2)
{
  CBaseList *v3; // rcx
  int v5; // edx
  int v6; // eax
  unsigned int v7; // r9d
  int v8; // edi
  bool v10; // zf
  int v11; // ebp
  unsigned __int64 v12; // rcx
  int v13; // eax
  int v14; // r8d
  unsigned int v15; // edx
  struct CSAMIInterpreter::CStreamInfo *v16; // rdx
  struct CSAMIInterpreter::CStreamInfo *v17; // rax
  int v18; // r13d
  int v19; // r8d
  int i; // r14d
  LPCSTR *v21; // rdi
  int v22; // r15d
  int v23; // r14d
  LPCSTR *NextI; // rax
  int v25; // r8d
  int v26; // ecx
  bool v27; // cf
  int v28; // r14d
  int v29; // r15d
  int v30; // r14d
  __int64 v31; // r13
  unsigned __int64 v32; // r15
  char *v33; // rcx
  int v34; // r11d
  int j; // eax
  struct __POSITION *v36; // r15
  const CHAR *v37; // r13
  char **v38; // r15
  struct __POSITION *v39; // r13
  char *v40; // rax
  unsigned int v41; // edx
  char *v42; // rax
  unsigned __int64 v43; // r13
  char *v44; // rax
  char **v45; // r15
  char *v46; // rax
  unsigned int v47; // edx
  struct __POSITION *v48; // r13
  char *v49; // rax
  unsigned __int64 v50; // [rsp+30h] [rbp-48h]
  struct __POSITION *v51; // [rsp+80h] [rbp+8h] BYREF
  int v52; // [rsp+90h] [rbp+18h]
  struct __POSITION *v53; // [rsp+98h] [rbp+20h] BYREF

  v3 = (CBaseList *)*((unsigned int *)this + 212);
  if ( !(_DWORD)v3 && *(_DWORD *)a2 )
    return 2147942487LL;
  v5 = *(_DWORD *)a2;
  v6 = 5;
  LODWORD(v51) = 0;
  v7 = 0;
  if ( v5 > 5 )
  {
    if ( v5 != 6 )
    {
      switch ( v5 )
      {
        case 7:
          if ( *((_DWORD *)a2 + 2) != 1 )
            return 2147942487LL;
          v8 = 2;
          if ( !*((_DWORD *)a2 + 5243) )
          {
            if ( (_DWORD)v3 != 2 )
              return 2147942487LL;
            ++*((_DWORD *)this + 222);
            if ( *((int *)this + 202) < 50 )
            {
              v32 = lstrlenA((LPCSTR)a2 + 12) + 1;
              *((_QWORD *)this + 2 * *((int *)this + 202) + 1) = operator new[](v32);
              v33 = (char *)*((_QWORD *)this + 2 * *((int *)this + 202) + 1);
              if ( v33 )
              {
                StringCchCopyA(v33, v32, (const char *)a2 + 12);
                *((_DWORD *)this + 4 * (*((_DWORD *)this + 202))++ + 4) = v34;
              }
              v7 = (unsigned int)v51;
            }
            goto LABEL_28;
          }
          v10 = (_DWORD)v3 == 7;
LABEL_22:
          if ( !v10 )
            return 2147942487LL;
LABEL_28:
          *((_DWORD *)this + 212) = v8;
          return v7;
        case 8:
          if ( *((_DWORD *)a2 + 5243) )
          {
            v28 = 12;
            goto LABEL_104;
          }
          if ( (_DWORD)v3 != 3 )
            return 2147942487LL;
          break;
        case 9:
          if ( !*((_DWORD *)a2 + 5243) )
          {
            v29 = 0;
            v30 = 0;
            if ( *((int *)a2 + 2) <= 0 )
              return 2147942487LL;
            do
            {
              v31 = 1048LL * v30;
              if ( CompareStringA(0x7Fu, 1u, "start", -1, (PCNZCH)a2 + v31 + 12, -1) == 2 )
              {
                v29 = 1;
                *((_DWORD *)this + 214) = atoi((const char *)a2 + v31 + 32);
              }
              ++v30;
            }
            while ( v30 < *((_DWORD *)a2 + 2) );
            if ( !v29 )
              return 2147942487LL;
            v28 = 11;
            goto LABEL_88;
          }
          if ( (unsigned int)((_DWORD)v3 - 10) > 1 )
            return 2147942487LL;
          break;
        case 10:
          if ( *((_DWORD *)a2 + 5243) )
          {
            if ( (_DWORD)v3 != 10 )
              return 2147942487LL;
            v28 = 11;
LABEL_104:
            *((_DWORD *)this + 212) = v28;
            return v7;
          }
          if ( (unsigned int)((_DWORD)v3 - 10) > 1 || !*((_DWORD *)this + 221) )
            return 2147942487LL;
          v18 = 0;
          v19 = -1;
          v52 = -1;
          for ( i = 0; i < *((_DWORD *)a2 + 2); ++i )
          {
            v53 = (struct __POSITION *)(1048LL * i);
            if ( CompareStringA(0x7Fu, 1u, "class", -1, (PCNZCH)v53 + (_QWORD)a2 + 12, -1) == 2 )
            {
              v19 = i;
              v52 = i;
            }
            else
            {
              if ( CompareStringA(0x7Fu, 1u, "ID", -1, (PCNZCH)v53 + (_QWORD)a2 + 12, -1) == 2
                && CompareStringA(0x7Fu, 1u, "Source", -1, (PCNZCH)v53 + (_QWORD)a2 + 32, -1) == 2 )
              {
                v18 = 1;
              }
              v19 = v52;
            }
          }
          *((_DWORD *)this + 216) = v18;
          v21 = 0;
          v22 = 0;
          v23 = 0;
          if ( v19 != -1 )
          {
            v53 = (struct __POSITION *)*((_QWORD *)this + 112);
            while ( 1 )
            {
              NextI = (LPCSTR *)CBaseList::GetNextI(v3, &v53);
              v21 = NextI;
              if ( !NextI )
                break;
              if ( !lstrcmpA(*NextI, (LPCSTR)a2 + 1048 * v25 + 32) )
              {
                v23 = 1;
                break;
              }
              ++v22;
            }
          }
          v26 = -1;
          if ( v23 )
            v26 = v22;
          v27 = v23 != 0;
          v28 = 10;
          *((_QWORD *)this + 122) = (unsigned __int64)v21 & -(__int64)v27;
          *((_DWORD *)this + 215) = v26;
LABEL_88:
          v7 = (unsigned int)v51;
          goto LABEL_104;
        default:
          if ( v5 >= 100 && v5 < *((_DWORD *)this + 221) + 100 )
            *((_DWORD *)this + 215) = v5 - 100;
          return v7;
      }
      v28 = 8;
      goto LABEL_104;
    }
    if ( (_DWORD)v3 != 6 )
      return v7;
    for ( j = 0; ; j = v52 + 1 )
    {
      v52 = j;
      if ( j >= *((_DWORD *)a2 + 2) )
        return (unsigned int)v51;
      v36 = (struct __POSITION *)(1048LL * j);
      v37 = (char *)a2 + (_QWORD)v36 + 12;
      v53 = v36;
      if ( *v37 == 46 )
      {
        v38 = (char **)operator new(0x60u);
        if ( !v38 )
          return 2147942414LL;
        v39 = v53;
        *v38 = 0;
        v38[1] = 0;
        v38[2] = 0;
        v38[3] = 0;
        *((_DWORD *)v38 + 8) = 0;
        v38[5] = (char *)10;
        v38[6] = 0;
        v38[7] = 0;
        v38[8] = 0;
        *((_DWORD *)v38 + 18) = 0;
        v38[10] = (char *)10;
        v38[11] = 0;
        v53 = (struct __POSITION *)(lstrlenA((LPCSTR)v39 + (_QWORD)a2 + 13) + 1);
        v40 = (char *)operator new[]((unsigned __int64)v53);
        *v38 = v40;
        if ( !v40
          || (StringCchCopyA(v40, (unsigned __int64)v53, (const char *)v39 + (_QWORD)a2 + 13),
              v53 = (struct __POSITION *)(lstrlenA((LPCSTR)v39 + (_QWORD)a2 + 32) + 1),
              v42 = (char *)operator new[]((unsigned __int64)v53),
              (v38[1] = v42) == 0)
          || (StringCchCopyA(v42, (unsigned __int64)v53, (const char *)v39 + (_QWORD)a2 + 32),
              !CBaseList::AddTailI((CSAMIInterpreter *)((char *)this + 896), v38)) )
        {
          CSAMIInterpreter::CStreamInfo::`scalar deleting destructor'((CSAMIInterpreter::CStreamInfo *)v38, v41);
          return 2147942414LL;
        }
        ++*((_DWORD *)this + 221);
      }
      else
      {
        if ( *v37 != 35 )
        {
          if ( CompareStringA(0x7Fu, 1u, "P", -1, (PCNZCH)a2 + (_QWORD)v36 + 12, -1) != 2 )
            continue;
          v43 = lstrlenA((LPCSTR)a2 + (_QWORD)v36 + 32) + 1;
          v44 = (char *)operator new[](v43);
          *((_QWORD *)this + 126) = v44;
          goto LABEL_132;
        }
        if ( CompareStringA(0x7Fu, 1u, "Source", -1, v37 + 1, -1) == 2 )
        {
          v43 = lstrlenA((LPCSTR)a2 + (_QWORD)v36 + 32) + 1;
          v44 = (char *)operator new[](v43);
          *((_QWORD *)this + 125) = v44;
LABEL_132:
          if ( !v44 )
            return 2147942414LL;
          StringCchCopyA(v44, v43, (const char *)a2 + (_QWORD)v36 + 32);
          continue;
        }
        v45 = (char **)operator new(0x10u);
        if ( !v45 )
          return 2147942414LL;
        v50 = lstrlenA(v37);
        v46 = (char *)operator new[](v50);
        *v45 = v46;
        if ( !v46
          || (StringCchCopyA(v46, v50, v37 + 1),
              v48 = v53,
              v53 = (struct __POSITION *)(lstrlenA((LPCSTR)v53 + (_QWORD)a2 + 32) + 1),
              v49 = (char *)operator new[]((unsigned __int64)v53),
              (v45[1] = v49) == 0)
          || (StringCchCopyA(v49, (unsigned __int64)v53, (const char *)v48 + (_QWORD)a2 + 32),
              !CBaseList::AddTailI((CSAMIInterpreter *)((char *)this + 936), v45)) )
        {
          CSAMIInterpreter::CStyleInfo::`scalar deleting destructor'((CSAMIInterpreter::CStyleInfo *)v45, v47);
          return 2147942414LL;
        }
      }
    }
  }
  switch ( v5 )
  {
    case 5:
      if ( !*((_DWORD *)a2 + 5243) )
      {
        if ( (_DWORD)v3 != 2 || *((_DWORD *)this + 221) )
          return 2147942487LL;
        v8 = 6;
        goto LABEL_28;
      }
      if ( (_DWORD)v3 != 6 || !*((_DWORD *)this + 221) )
        return 2147942487LL;
LABEL_26:
      v8 = 2;
      goto LABEL_28;
    case -1:
      v12 = (unsigned int)((_DWORD)v3 - 9);
      if ( !(_DWORD)v12 )
      {
        *((_QWORD *)this + 109) = *((_QWORD *)a2 + 1);
        *((_DWORD *)this + 220) = *((_DWORD *)a2 + 4);
        return v7;
      }
      if ( (_DWORD)v12 != 1 )
        return v7;
      v13 = *((_DWORD *)this + 214);
      v14 = *((_DWORD *)this + 248);
      if ( *((_DWORD *)this + 216) )
      {
        if ( v14 == v13 )
        {
          *((_DWORD *)this + 247) += *((_DWORD *)a2 + 4);
        }
        else
        {
          v12 = *((unsigned int *)a2 + 4);
          if ( (unsigned int)v12 > *((_DWORD *)this + 247) )
          {
            *((_DWORD *)this + 247) = v12;
LABEL_44:
            *((_DWORD *)this + 248) = v13;
          }
        }
      }
      else
      {
        v12 = *((unsigned int *)a2 + 4);
        v15 = *((_DWORD *)this + 246);
        if ( v14 == v13 )
        {
          *((_DWORD *)this + 246) = v15 + v12;
          goto LABEL_46;
        }
        if ( (unsigned int)v12 > v15 )
        {
          *((_DWORD *)this + 246) = v12;
          goto LABEL_44;
        }
      }
LABEL_46:
      v16 = (struct CSAMIInterpreter::CStreamInfo *)*((_QWORD *)this + 122);
      if ( v16 )
      {
        v7 = CSAMIInterpreter::AddEntry(this, v16, a2);
      }
      else
      {
        v51 = (struct __POSITION *)*((_QWORD *)this + 112);
        do
        {
          v17 = (struct CSAMIInterpreter::CStreamInfo *)CBaseList::GetNextI((CBaseList *)v12, &v51);
          if ( !v17 )
            break;
          v7 = CSAMIInterpreter::AddEntry(this, v17, a2);
        }
        while ( (v7 & 0x80000000) == 0 );
      }
      *((_DWORD *)this + 249) = *((_DWORD *)this + 214);
      return v7;
    case 0:
      if ( *((_DWORD *)a2 + 5243) )
      {
        v11 = 13;
      }
      else
      {
        if ( (_DWORD)v3 )
          return 2147942487LL;
        v11 = 1;
      }
      *((_DWORD *)this + 212) = v11;
      return v7;
    case 1:
      if ( *((_DWORD *)a2 + 5243) )
      {
        v8 = 3;
        goto LABEL_28;
      }
      if ( (_DWORD)v3 != 1 )
        return 2147942487LL;
      goto LABEL_26;
  }
  v8 = 2;
  if ( v5 == 2 )
  {
    if ( *((_DWORD *)a2 + 5243) )
      v10 = (_DWORD)v3 == 4;
    else
      v10 = (_DWORD)v3 == 2;
    goto LABEL_22;
  }
  if ( v5 == 3 )
  {
    if ( *((_DWORD *)a2 + 5243) )
    {
      if ( (_DWORD)v3 == 5 )
      {
        v6 = 2;
LABEL_18:
        *((_DWORD *)this + 212) = v6;
        return v7;
      }
    }
    else if ( (_DWORD)v3 == 2 )
    {
      goto LABEL_18;
    }
    return 2147942487LL;
  }
  if ( v5 == 4 && (_DWORD)v3 != 2 )
    return 2147942487LL;
  return v7;
}

```

## disassembly

```asm
0x180124250  mov     [rsp+arg_8], rbx
0x180124255  push    rbp
0x180124256  push    rsi
0x180124257  push    rdi
0x180124258  push    r12
0x18012425a  push    r13
0x18012425c  push    r14
0x18012425e  push    r15
0x180124260  sub     rsp, 40h
0x180124264  mov     rbx, rcx
0x180124267  xor     r10d, r10d
0x18012426a  mov     ecx, [rcx+350h]
0x180124270  mov     rsi, rdx
0x180124273  test    ecx, ecx
0x180124275  jnz     short loc_18012427C
0x180124277  cmp     [rdx], r10d
0x18012427a  jnz     short loc_1801242D5
0x18012427c  mov     edx, [rdx]
0x18012427e  mov     eax, 5
0x180124283  mov     dword ptr [rsp+78h+arg_0], r10d
0x18012428b  mov     r9d, r10d
0x18012428e  cmp     edx, eax
0x180124290  jg      loc_180124495
0x180124296  jz      loc_180124449
0x18012429c  or      r12d, 0FFFFFFFFh
0x1801242a0  cmp     edx, r12d
0x1801242a3  jz      loc_180124359
0x1801242a9  test    edx, edx
0x1801242ab  jz      loc_180124337
0x1801242b1  lea     ebp, [rax-4]
0x1801242b4  cmp     edx, ebp
0x1801242b6  jz      short loc_180124313
0x1801242b8  lea     edi, [rax-3]
0x1801242bb  cmp     edx, edi
0x1801242bd  jz      short loc_1801242FF
0x1801242bf  cmp     edx, 3
0x1801242c2  jz      short loc_1801242DF
0x1801242c4  cmp     edx, 4
0x1801242c7  jnz     loc_180124B6A
0x1801242cd  cmp     ecx, edi
0x1801242cf  jz      loc_180124B6A
0x1801242d5  mov     eax, 80070057h
0x1801242da  jmp     loc_180124B6D
0x1801242df  cmp     [rsi+51ECh], r10d
0x1801242e6  jnz     short loc_1801242EE
0x1801242e8  cmp     ecx, edi
0x1801242ea  jnz     short loc_1801242D5
0x1801242ec  jmp     short loc_1801242F4
0x1801242ee  cmp     ecx, eax
0x1801242f0  jnz     short loc_1801242D5
0x1801242f2  mov     eax, edi
0x1801242f4  mov     [rbx+350h], eax
0x1801242fa  jmp     loc_180124B6A
0x1801242ff  cmp     [rsi+51ECh], r10d
0x180124306  jnz     short loc_18012430C
0x180124308  cmp     ecx, edi
0x18012430a  jmp     short loc_18012430F
0x18012430c  cmp     ecx, 4
0x18012430f  jnz     short loc_1801242D5
0x180124311  jmp     short loc_18012432C
0x180124313  cmp     [rsi+51ECh], r10d
0x18012431a  jnz     short loc_180124327
0x18012431c  cmp     ecx, ebp
0x18012431e  jnz     short loc_1801242D5
0x180124320  mov     edi, 2
0x180124325  jmp     short loc_18012432C
0x180124327  mov     edi, 3
0x18012432c  mov     [rbx+350h], edi
0x180124332  jmp     loc_180124B6A
0x180124337  cmp     [rsi+51ECh], r10d
0x18012433e  jnz     short loc_180124349
0x180124340  test    ecx, ecx
0x180124342  jnz     short loc_1801242D5
0x180124344  lea     ebp, [rcx+1]
0x180124347  jmp     short loc_18012434E
0x180124349  mov     ebp, 0Dh
0x18012434e  mov     [rbx+350h], ebp
0x180124354  jmp     loc_180124B6A
0x180124359  sub     ecx, 9
0x18012435c  jz      loc_180124430
0x180124362  cmp     ecx, 1
0x180124365  jnz     loc_180124B6A
0x18012436b  mov     eax, [rbx+358h]
0x180124371  mov     r8d, [rbx+3E0h]
0x180124378  cmp     [rbx+360h], r10d
0x18012437f  jz      short loc_1801243A4
0x180124381  cmp     r8d, eax
0x180124384  jz      short loc_180124399
0x180124386  mov     ecx, [rsi+10h]
0x180124389  cmp     ecx, [rbx+3DCh]
0x18012438f  jbe     short loc_1801243CD
0x180124391  mov     [rbx+3DCh], ecx
0x180124397  jmp     short loc_1801243BC
0x180124399  mov     eax, [rsi+10h]
0x18012439c  add     [rbx+3DCh], eax
0x1801243a2  jmp     short loc_1801243CD
0x1801243a4  mov     ecx, [rsi+10h]; this
0x1801243a7  mov     edx, [rbx+3D8h]
0x1801243ad  cmp     r8d, eax
0x1801243b0  jz      short loc_1801243C4
0x1801243b2  cmp     ecx, edx
0x1801243b4  jbe     short loc_1801243CD
0x1801243b6  mov     [rbx+3D8h], ecx
0x1801243bc  mov     [rbx+3E0h], eax
0x1801243c2  jmp     short loc_1801243CD
0x1801243c4  lea     eax, [rdx+rcx]
0x1801243c7  mov     [rbx+3D8h], eax
0x1801243cd  mov     rdx, [rbx+3D0h]; struct CSAMIInterpreter::CStreamInfo *
0x1801243d4  test    rdx, rdx
0x1801243d7  jz      short loc_1801243E9
0x1801243d9  mov     r8, rsi; struct CToken *
0x1801243dc  mov     rcx, rbx; this
0x1801243df  call    ?AddEntry@CSAMIInterpreter@@QEAAJPEAVCStreamInfo@1@AEAVCToken@@@Z; CSAMIInterpreter::AddEntry(CSAMIInterpreter::CStreamInfo *,CToken &)
0x1801243e4  mov     r9d, eax
0x1801243e7  jmp     short loc_18012441F
0x1801243e9  mov     rax, [rbx+380h]
0x1801243f0  mov     [rsp+78h+arg_0], rax
0x1801243f8  lea     rdx, [rsp+78h+arg_0]; struct __POSITION **
0x180124400  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x180124405  test    rax, rax
0x180124408  jz      short loc_18012441F
0x18012440a  mov     r8, rsi; struct CToken *
0x18012440d  mov     rdx, rax; struct CSAMIInterpreter::CStreamInfo *
0x180124410  mov     rcx, rbx; this
0x180124413  call    ?AddEntry@CSAMIInterpreter@@QEAAJPEAVCStreamInfo@1@AEAVCToken@@@Z; CSAMIInterpreter::AddEntry(CSAMIInterpreter::CStreamInfo *,CToken &)
0x180124418  mov     r9d, eax
0x18012441b  test    eax, eax
0x18012441d  jns     short loc_1801243F8
0x18012441f  mov     eax, [rbx+358h]
0x180124425  mov     [rbx+3E4h], eax
0x18012442b  jmp     loc_180124B6A
0x180124430  mov     rax, [rsi+8]
0x180124434  mov     [rbx+368h], rax
0x18012443b  mov     eax, [rsi+10h]
0x18012443e  mov     [rbx+370h], eax
0x180124444  jmp     loc_180124B6A
0x180124449  cmp     [rsi+51ECh], r10d
0x180124450  jnz     short loc_180124476
0x180124452  mov     edi, 2
0x180124457  cmp     ecx, edi
0x180124459  jnz     loc_1801242D5
0x18012445f  cmp     [rbx+374h], r10d
0x180124466  ja      loc_1801242D5
0x18012446c  mov     edi, 6
0x180124471  jmp     loc_18012432C
0x180124476  mov     edi, 6
0x18012447b  cmp     ecx, edi
0x18012447d  jnz     loc_1801242D5
0x180124483  cmp     [rbx+374h], r10d
0x18012448a  jz      loc_1801242D5
0x180124490  jmp     loc_180124320
0x180124495  mov     r8d, edx
0x180124498  mov     edi, 6
0x18012449d  sub     r8d, edi
0x1801244a0  jz      loc_180124872
0x1801244a6  sub     r8d, 1
0x1801244aa  jz      loc_1801247B1
0x1801244b0  sub     r8d, 1
0x1801244b4  jz      loc_180124785
0x1801244ba  sub     r8d, 1
0x1801244be  jz      loc_1801246D5
0x1801244c4  cmp     r8d, 1
0x1801244c8  jz      short loc_1801244F2
0x1801244ca  cmp     edx, 64h ; 'd'
0x1801244cd  jl      loc_180124B6A
0x1801244d3  mov     eax, [rbx+374h]
0x1801244d9  add     eax, 64h ; 'd'
0x1801244dc  cmp     edx, eax
0x1801244de  jge     loc_180124B6A
0x1801244e4  lea     eax, [rdx-64h]
0x1801244e7  mov     [rbx+35Ch], eax
0x1801244ed  jmp     loc_180124B6A
0x1801244f2  cmp     [rsi+51ECh], r10d
0x1801244f9  jnz     loc_1801246BB
0x1801244ff  lea     eax, [rcx-0Ah]
0x180124502  mov     ebp, 1
0x180124507  cmp     eax, ebp
0x180124509  ja      loc_1801242D5
0x18012450f  cmp     [rbx+374h], r10d
0x180124516  jz      loc_1801242D5
0x18012451c  or      r12d, 0FFFFFFFFh
0x180124520  mov     r13d, r10d
0x180124523  mov     r8d, r12d
0x180124526  mov     [rsp+78h+arg_10], r12d
0x18012452e  mov     r14d, r10d
0x180124531  cmp     [rsi+8], r10d
0x180124535  jle     loc_18012461B
0x18012453b  lea     edi, [rbp+1]
0x18012453e  lea     r15d, [rbp+7Eh]
0x180124542  movsxd  rax, r14d
0x180124545  lea     r8, aClass; "class"
0x18012454c  imul    rax, 418h
0x180124553  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x180124558  mov     r9d, r12d; cchCount1
0x18012455b  mov     [rsp+78h+arg_18], rax
0x180124563  mov     edx, ebp; dwCmpFlags
0x180124565  add     rax, 0Ch
0x180124569  mov     ecx, r15d; Locale
0x18012456c  add     rax, rsi
0x18012456f  mov     [rsp+78h+lpString2], rax; lpString2
0x180124574  call    cs:__imp_CompareStringA
0x18012457b  nop     dword ptr [rax+rax+00h]
0x180124580  cmp     eax, edi
0x180124582  jnz     short loc_180124591
0x180124584  mov     r8d, r14d
0x180124587  mov     [rsp+78h+arg_10], r14d
0x18012458f  jmp     short loc_18012460B
0x180124591  mov     rax, [rsp+78h+arg_18]
0x180124599  lea     r8, aId; "ID"
0x1801245a0  add     rax, 0Ch
0x1801245a4  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801245a9  add     rax, rsi
0x1801245ac  mov     r9d, r12d; cchCount1
0x1801245af  mov     edx, ebp; dwCmpFlags
0x1801245b1  mov     [rsp+78h+lpString2], rax; lpString2
0x1801245b6  mov     ecx, r15d; Locale
0x1801245b9  call    cs:__imp_CompareStringA
0x1801245c0  nop     dword ptr [rax+rax+00h]
0x1801245c5  cmp     eax, edi
0x1801245c7  jnz     short loc_180124603
0x1801245c9  mov     rax, [rsp+78h+arg_18]
0x1801245d1  lea     r8, aSource; "Source"
0x1801245d8  add     rax, 20h ; ' '
0x1801245dc  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801245e1  add     rax, rsi
0x1801245e4  mov     r9d, r12d; cchCount1
0x1801245e7  mov     edx, ebp; dwCmpFlags
0x1801245e9  mov     [rsp+78h+lpString2], rax; lpString2
0x1801245ee  mov     ecx, r15d; Locale
0x1801245f1  call    cs:__imp_CompareStringA
0x1801245f8  nop     dword ptr [rax+rax+00h]
0x1801245fd  cmp     eax, edi
0x1801245ff  cmovz   r13d, ebp
0x180124603  mov     r8d, [rsp+78h+arg_10]
0x18012460b  add     r14d, ebp
0x18012460e  cmp     r14d, [rsi+8]
0x180124612  jl      loc_180124542
0x180124618  xor     r10d, r10d
0x18012461b  mov     [rbx+360h], r13d
0x180124622  mov     rdi, r10
0x180124625  mov     r15d, r10d
0x180124628  mov     r14d, r10d
0x18012462b  cmp     r8d, r12d
0x18012462e  jz      short loc_180124688
0x180124630  mov     rax, [rbx+380h]
0x180124637  mov     [rsp+78h+arg_18], rax
0x18012463f  lea     rdx, [rsp+78h+arg_18]; struct __POSITION **
0x180124647  call    ?GetNextI@CBaseList@@IEBAPEAXAEAPEAU__POSITION@@@Z; CBaseList::GetNextI(__POSITION * &)
0x18012464c  mov     rdi, rax
0x18012464f  test    rax, rax
0x180124652  jz      short loc_180124688
0x180124654  movsxd  rcx, r8d
0x180124657  imul    rdx, rcx, 418h
0x18012465e  mov     rcx, [rax]; lpString1
0x180124661  add     rdx, 20h ; ' '
0x180124665  add     rdx, rsi; lpString2
0x180124668  call    cs:__imp_lstrcmpA
0x18012466f  nop     dword ptr [rax+rax+00h]
0x180124674  test    eax, eax
0x180124676  jz      short loc_180124685
0x180124678  mov     r8d, [rsp+78h+arg_10]
0x180124680  add     r15d, ebp
0x180124683  jmp     short loc_18012463F
0x180124685  mov     r14d, ebp
0x180124688  or      ecx, 0FFFFFFFFh
0x18012468b  test    r14d, r14d
0x18012468e  cmovnz  ecx, r15d
0x180124692  neg     r14d
0x180124695  mov     r14d, 0Ah
0x18012469b  sbb     rax, rax
0x18012469e  and     rax, rdi
0x1801246a1  mov     [rbx+3D0h], rax
0x1801246a8  mov     [rbx+35Ch], ecx
0x1801246ae  mov     r9d, dword ptr [rsp+78h+arg_0]
0x1801246b6  jmp     loc_1801247A5
0x1801246bb  mov     r14d, 0Ah
0x1801246c1  cmp     ecx, r14d
0x1801246c4  jnz     loc_1801242D5
0x1801246ca  mov     r14d, 0Bh
0x1801246d0  jmp     loc_1801247A5
0x1801246d5  cmp     [rsi+51ECh], r10d
0x1801246dc  jnz     loc_180124773
0x1801246e2  mov     r15d, r10d
0x1801246e5  mov     r14d, r10d
0x1801246e8  cmp     [rsi+8], r10d
0x1801246ec  jle     loc_1801242D5
0x1801246f2  or      r12d, 0FFFFFFFFh
0x1801246f6  lea     ebp, [r12+2]
0x1801246fb  lea     edi, [rbp+1]
0x1801246fe  movsxd  rax, r14d
0x180124701  lea     r8, aStart; "start"
0x180124708  imul    r13, rax, 418h
0x18012470f  lea     rax, [rsi+0Ch]
0x180124713  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x180124718  add     rax, r13
0x18012471b  mov     r9d, r12d; cchCount1
0x18012471e  mov     edx, ebp; dwCmpFlags
0x180124720  mov     [rsp+78h+lpString2], rax; lpString2
0x180124725  mov     ecx, 7Fh; Locale
0x18012472a  call    cs:__imp_CompareStringA
  ... truncated ...
```
