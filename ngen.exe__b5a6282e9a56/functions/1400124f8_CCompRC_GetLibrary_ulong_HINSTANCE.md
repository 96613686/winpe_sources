# CCompRC::GetLibrary(ulong,HINSTANCE__ * *)

- ea: `0x1400124f8`
- end: `0x14001278a`
- name: `?GetLibrary@CCompRC@@AEAAJKPEAPEAUHINSTANCE__@@@Z`
- size: `658`
- prototype: `__int64 __fastcall(CCompRC *__hidden this, unsigned int, HINSTANCE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001181c`

## callees

- `0x14000a1f4`
- `0x14000a218`
- `0x14000d004`
- `0x140012280`
- `0x1400122e4`
- `0x1400124f8`
- `0x140012c84`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140012619`
- `KERNEL32!FreeLibrary` at `0x14001275b`
- `KERNEL32!FreeLibrary` at `0x140012619`
- `KERNEL32!FreeLibrary` at `0x14001275b`

## pseudocode

```c
__int64 __fastcall CCompRC::GetLibrary(CCompRC *this, unsigned int a2, HINSTANCE *a3)
{
  int v5; // ebx
  HMODULE v6; // r15
  int v7; // r13d
  int v9; // eax
  void *v10; // r14
  int v11; // esi
  HMODULE v12; // rcx
  void *v13; // r14
  int v14; // esi
  int v15; // eax
  void *v16; // r14
  int v17; // esi
  const struct NoThrow *v18; // rdx
  HMODULE v19; // r13
  int v20; // edi
  HMODULE hLibModule; // [rsp+20h] [rbp-20h] BYREF
  void *v22; // [rsp+28h] [rbp-18h]
  int v23; // [rsp+30h] [rbp-10h]
  int v24; // [rsp+80h] [rbp+40h]
  int v26; // [rsp+98h] [rbp+58h] BYREF

  v5 = -2147467259;
  v6 = 0;
  hLibModule = 0;
  v7 = 0;
  v24 = 0;
  if ( *((_QWORD *)this + 1) )
  {
    if ( a2 == -1 || a2 == *(_DWORD *)this )
    {
      v6 = (HMODULE)*((_QWORD *)this + 1);
      goto LABEL_5;
    }
  }
  else if ( *((_DWORD *)this + 4) )
  {
    v5 = -2147024894;
  }
  else
  {
    v9 = CCompRC::LoadLibrary(this, &hLibModule);
    v5 = v9;
    if ( v9 < 0 && (unsigned int)Exception::IsTransient(v9) )
      return (unsigned int)v5;
    v10 = (void *)*((_QWORD *)this + 5);
    v22 = v10;
    v11 = 0;
    v23 = 0;
    if ( v10 )
    {
      ClrEnterCriticalSection(v10);
      v11 = 1;
      v23 = 1;
    }
    v12 = hLibModule;
    if ( *((_QWORD *)this + 1) || *((_DWORD *)this + 4) )
    {
      if ( a2 != -1 && a2 == *(_DWORD *)this )
        v6 = (HMODULE)*((_QWORD *)this + 1);
      v24 = 1;
      v7 = 1;
    }
    else
    {
      v6 = hLibModule;
      if ( v5 < 0 )
        *((_DWORD *)this + 4) = 1;
      else
        *((_QWORD *)this + 1) = hLibModule;
      *(_DWORD *)this = a2;
    }
    if ( v5 < 0 )
    {
      if ( v11 )
      {
        ClrLeaveCriticalSection(v10);
        v23 = 0;
      }
      return (unsigned int)v5;
    }
    if ( v7 )
    {
      FreeLibrary(v12);
      v24 = 0;
    }
    if ( v11 )
    {
      ClrLeaveCriticalSection(v10);
      v23 = 0;
    }
    if ( v6 )
      goto LABEL_6;
  }
  if ( *((_DWORD *)this + 4) )
    goto LABEL_6;
  v13 = (void *)*((_QWORD *)this + 5);
  v22 = v13;
  v14 = 0;
  v23 = 0;
  if ( v13 )
  {
    ClrEnterCriticalSection(v13);
    v14 = 1;
    v23 = 1;
  }
  v26 = 0;
  v6 = CCompRC::LookupNode(this, a2, &v26);
  if ( v26 == 1 )
  {
    v5 = -2147024894;
    if ( v14 )
    {
      ClrLeaveCriticalSection(v13);
      v23 = 0;
    }
    goto LABEL_6;
  }
  if ( v14 )
  {
    ClrLeaveCriticalSection(v13);
    v23 = 0;
  }
  if ( v6 )
  {
LABEL_5:
    v5 = 0;
LABEL_6:
    *a3 = v6;
    return (unsigned int)v5;
  }
  v15 = CCompRC::LoadLibrary(this, &hLibModule);
  v5 = v15;
  if ( v15 >= 0 || !(unsigned int)Exception::IsTransient(v15) )
  {
    v16 = (void *)*((_QWORD *)this + 5);
    v22 = v16;
    v17 = 0;
    v23 = 0;
    if ( v16 )
    {
      ClrEnterCriticalSection(v16);
      v17 = 1;
      v23 = 1;
    }
    v26 = 0;
    v6 = CCompRC::LookupNode(this, a2, &v26);
    v19 = hLibModule;
    if ( v6 || v26 )
    {
      v20 = 1;
    }
    else
    {
      if ( v5 < 0 )
      {
        v26 = v5;
        v5 = CCompRC::AddMapNode(this, v18, 0, 1);
        if ( v5 >= 0 )
          v5 = v26;
      }
      else
      {
        v6 = hLibModule;
        v5 = CCompRC::AddMapNode(this, v18, hLibModule, 0);
      }
      v20 = v24;
    }
    if ( v17 )
    {
      ClrLeaveCriticalSection(v16);
      v23 = 0;
    }
    if ( v20 || v5 < 0 )
      FreeLibrary(v19);
    goto LABEL_6;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400124f8  mov     [rsp-38h+arg_8], rbx
0x1400124fd  mov     [rsp-38h+arg_10], r8
0x140012502  push    rbp
0x140012503  push    rsi
0x140012504  push    rdi
0x140012505  push    r12
0x140012507  push    r13
0x140012509  push    r14
0x14001250b  push    r15
0x14001250d  mov     rbp, rsp
0x140012510  sub     rsp, 40h
0x140012514  mov     r12d, edx
0x140012517  mov     rdi, rcx
0x14001251a  mov     ebx, 80004005h
0x14001251f  xor     r15d, r15d
0x140012522  and     [rbp+hLibModule], r15
0x140012526  xor     r13d, r13d
0x140012529  mov     [rbp+arg_0], r13d
0x14001252d  mov     rax, [rcx+8]
0x140012531  test    rax, rax
0x140012534  jz      short loc_140012569
0x140012536  cmp     edx, 0FFFFFFFFh
0x140012539  jz      short loc_140012543
0x14001253b  cmp     edx, [rcx]
0x14001253d  jnz     loc_14001263C
0x140012543  mov     r15, rax
0x140012546  xor     ebx, ebx
0x140012548  mov     rax, [rbp+arg_10]
0x14001254c  mov     [rax], r15
0x14001254f  mov     eax, ebx
0x140012551  mov     rbx, [rsp+40h+arg_8]
0x140012559  add     rsp, 40h
0x14001255d  pop     r15
0x14001255f  pop     r14
0x140012561  pop     r13
0x140012563  pop     r12
0x140012565  pop     rdi
0x140012566  pop     rsi
0x140012567  pop     rbp
0x140012568  retn
0x140012569  cmp     [rcx+10h], r13d
0x14001256d  jz      short loc_140012579
0x14001256f  mov     ebx, 80070002h
0x140012574  jmp     loc_14001263C
0x140012579  lea     rdx, [rbp+hLibModule]; HINSTANCE *
0x14001257d  call    ?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z; CCompRC::LoadLibrary(HINSTANCE__ * *)
0x140012582  mov     ebx, eax
0x140012584  test    eax, eax
0x140012586  jns     short loc_140012593
0x140012588  mov     ecx, eax; int
0x14001258a  call    ?IsTransient@Exception@@SAHJ@Z; Exception::IsTransient(long)
0x14001258f  test    eax, eax
0x140012591  jnz     short loc_14001254F
0x140012593  mov     r14, [rdi+28h]
0x140012597  mov     [rbp+var_18], r14
0x14001259b  xor     esi, esi
0x14001259d  mov     [rbp+var_10], esi
0x1400125a0  test    r14, r14
0x1400125a3  jz      short loc_1400125B7
0x1400125a5  mov     rcx, r14; void *
0x1400125a8  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x1400125ad  lea     eax, [rsi+1]
0x1400125b0  mov     esi, eax
0x1400125b2  mov     [rbp+var_10], eax
0x1400125b5  jmp     short loc_1400125BC
0x1400125b7  mov     eax, 1
0x1400125bc  mov     rcx, [rbp+hLibModule]; hLibModule
0x1400125c0  cmp     qword ptr [rdi+8], 0
0x1400125c5  jnz     short loc_1400125E2
0x1400125c7  cmp     dword ptr [rdi+10h], 0
0x1400125cb  jnz     short loc_1400125E2
0x1400125cd  mov     r15, rcx
0x1400125d0  test    ebx, ebx
0x1400125d2  js      short loc_1400125DA
0x1400125d4  mov     [rdi+8], rcx
0x1400125d8  jmp     short loc_1400125DD
0x1400125da  mov     [rdi+10h], eax
0x1400125dd  mov     [rdi], r12d
0x1400125e0  jmp     short loc_1400125F7
0x1400125e2  cmp     r12d, 0FFFFFFFFh
0x1400125e6  jz      short loc_1400125F1
0x1400125e8  cmp     r12d, [rdi]
0x1400125eb  jnz     short loc_1400125F1
0x1400125ed  mov     r15, [rdi+8]
0x1400125f1  mov     [rbp+arg_0], eax
0x1400125f4  mov     r13d, eax
0x1400125f7  test    ebx, ebx
0x1400125f9  jns     short loc_140012614
0x1400125fb  test    esi, esi
0x1400125fd  jz      loc_14001254F
0x140012603  mov     rcx, r14; void *
0x140012606  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x14001260b  and     [rbp+var_10], 0
0x14001260f  jmp     loc_14001254F
0x140012614  test    r13d, r13d
0x140012617  jz      short loc_140012623
0x140012619  call    cs:__imp_FreeLibrary
0x14001261f  and     [rbp+arg_0], 0
0x140012623  test    esi, esi
0x140012625  jz      short loc_140012633
0x140012627  mov     rcx, r14; void *
0x14001262a  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x14001262f  and     [rbp+var_10], 0
0x140012633  test    r15, r15
0x140012636  jnz     loc_140012548
0x14001263c  cmp     dword ptr [rdi+10h], 0
0x140012640  jnz     loc_140012548
0x140012646  mov     r14, [rdi+28h]
0x14001264a  mov     [rbp+var_18], r14
0x14001264e  xor     esi, esi
0x140012650  mov     [rbp+var_10], esi
0x140012653  test    r14, r14
0x140012656  jz      short loc_140012668
0x140012658  mov     rcx, r14; void *
0x14001265b  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x140012660  mov     esi, 1
0x140012665  mov     [rbp+var_10], esi
0x140012668  and     [rbp+arg_18], 0
0x14001266c  lea     r8, [rbp+arg_18]; int *
0x140012670  mov     edx, r12d; unsigned int
0x140012673  mov     rcx, rdi; this
0x140012676  call    ?LookupNode@CCompRC@@AEAAPEAUHINSTANCE__@@KAEAH@Z; CCompRC::LookupNode(ulong,int &)
0x14001267b  mov     r15, rax
0x14001267e  cmp     [rbp+arg_18], 1
0x140012682  jnz     short loc_1400126A2
0x140012684  mov     ebx, 80070002h
0x140012689  test    esi, esi
0x14001268b  jz      loc_140012548
0x140012691  mov     rcx, r14; void *
0x140012694  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x140012699  and     [rbp+var_10], 0
0x14001269d  jmp     loc_140012548
0x1400126a2  test    esi, esi
0x1400126a4  jz      short loc_1400126B2
0x1400126a6  mov     rcx, r14; void *
0x1400126a9  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x1400126ae  and     [rbp+var_10], 0
0x1400126b2  test    r15, r15
0x1400126b5  jnz     loc_140012546
0x1400126bb  lea     rdx, [rbp+hLibModule]; HINSTANCE *
0x1400126bf  mov     rcx, rdi; this
0x1400126c2  call    ?LoadLibrary@CCompRC@@AEAAJPEAPEAUHINSTANCE__@@@Z; CCompRC::LoadLibrary(HINSTANCE__ * *)
0x1400126c7  mov     ebx, eax
0x1400126c9  test    eax, eax
0x1400126cb  jns     short loc_1400126DC
0x1400126cd  mov     ecx, eax; int
0x1400126cf  call    ?IsTransient@Exception@@SAHJ@Z; Exception::IsTransient(long)
0x1400126d4  test    eax, eax
0x1400126d6  jnz     loc_14001254F
0x1400126dc  mov     r14, [rdi+28h]
0x1400126e0  mov     [rbp+var_18], r14
0x1400126e4  xor     esi, esi
0x1400126e6  mov     [rbp+var_10], esi
0x1400126e9  test    r14, r14
0x1400126ec  jz      short loc_1400126FE
0x1400126ee  mov     rcx, r14; void *
0x1400126f1  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x1400126f6  mov     esi, 1
0x1400126fb  mov     [rbp+var_10], esi
0x1400126fe  and     [rbp+arg_18], 0
0x140012702  lea     r8, [rbp+arg_18]; int *
0x140012706  mov     edx, r12d; unsigned int
0x140012709  mov     rcx, rdi; this
0x14001270c  call    ?LookupNode@CCompRC@@AEAAPEAUHINSTANCE__@@KAEAH@Z; CCompRC::LookupNode(ulong,int &)
0x140012711  mov     r15, rax
0x140012714  mov     r13, [rbp+hLibModule]
0x140012718  test    rax, rax
0x14001271b  jnz     short loc_140012782
0x14001271d  cmp     [rbp+arg_18], eax
0x140012720  jnz     short loc_140012782
0x140012722  mov     rcx, rdi; this
0x140012725  test    ebx, ebx
0x140012727  js      short loc_140012766
0x140012729  mov     r15, r13
0x14001272c  xor     r9d, r9d; int
0x14001272f  mov     r8, r13; HINSTANCE
0x140012732  call    ?AddMapNode@CCompRC@@AEAAJKPEAUHINSTANCE__@@H@Z; CCompRC::AddMapNode(ulong,HINSTANCE__ *,int)
0x140012737  mov     ebx, eax
0x140012739  mov     edi, [rbp+arg_0]
0x14001273c  test    esi, esi
0x14001273e  jz      short loc_14001274C
0x140012740  mov     rcx, r14; void *
0x140012743  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x140012748  and     [rbp+var_10], 0
0x14001274c  test    edi, edi
0x14001274e  jnz     short loc_140012758
0x140012750  test    ebx, ebx
0x140012752  jns     loc_140012548
0x140012758  mov     rcx, r13; hLibModule
0x14001275b  call    cs:__imp_FreeLibrary
0x140012761  jmp     loc_140012548
0x140012766  mov     [rbp+arg_18], ebx
0x140012769  mov     r9d, 1; int
0x14001276f  xor     r8d, r8d; HINSTANCE
0x140012772  call    ?AddMapNode@CCompRC@@AEAAJKPEAUHINSTANCE__@@H@Z; CCompRC::AddMapNode(ulong,HINSTANCE__ *,int)
0x140012777  mov     ebx, eax
0x140012779  test    eax, eax
0x14001277b  js      short loc_140012739
0x14001277d  mov     ebx, [rbp+arg_18]
0x140012780  jmp     short loc_140012739
0x140012782  mov     edi, 1
0x140012787  jmp     short loc_14001273C
```
