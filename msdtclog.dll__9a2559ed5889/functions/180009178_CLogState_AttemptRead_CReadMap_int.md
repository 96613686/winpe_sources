# CLogState::AttemptRead(CReadMap &,int)

- ea: `0x180009178`
- end: `0x180009292`
- name: `?AttemptRead@CLogState@@QEAAXAEAVCReadMap@@H@Z`
- size: `282`
- prototype: `void __fastcall(CLogState *__hidden this, struct CReadMap *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002bf0`
- `0x180002ea0`
- `0x180007d7c`

## callees

- `0x180009178`
- `0x180009c40`
- `0x180009cd8`
- `0x18001266c`

## pseudocode

```c
void __fastcall CLogState::AttemptRead(CLogState *this, struct CReadMap *a2, int a3)
{
  int v4; // eax
  unsigned int v6; // eax
  unsigned int v7; // ecx
  int v8; // eax
  int v9; // ecx
  bool v10; // zf
  unsigned int v11; // eax
  _DWORD v12[4]; // [rsp+20h] [rbp-20h] BYREF
  int v13; // [rsp+30h] [rbp-10h]
  __int64 v14; // [rsp+34h] [rbp-Ch]
  int v15; // [rsp+3Ch] [rbp-4h]
  unsigned int pExceptionObject; // [rsp+60h] [rbp+20h] BYREF

  v4 = *((_DWORD *)a2 + 1) + 24;
  v12[1] = 0;
  v12[3] = 0;
  v15 = 0;
  pExceptionObject = v4;
  if ( !a3 )
  {
    v6 = *((_DWORD *)this + 6);
    v7 = *((_DWORD *)this + 8);
    if ( v7 > v6 && *(_DWORD *)a2 < v7 && *(_DWORD *)a2 >= v6 )
    {
      pExceptionObject = -1073737670;
      throw &pExceptionObject;
    }
  }
  v8 = *(_DWORD *)a2 - (*(_DWORD *)a2 & -*((_DWORD *)this + 20));
  v12[2] = *(_DWORD *)a2 & -*((_DWORD *)this + 20);
  v9 = *((_DWORD *)this + 7);
  v10 = *((_DWORD *)this + 26) == 0;
  v12[0] = v8 - 32;
  v13 = v9;
  v14 = 0;
  if ( !v10 )
  {
    v11 = *((_DWORD *)this + 8);
    if ( v11 > *((_DWORD *)this + 6) && *(_DWORD *)a2 >= v11 )
      v13 = v9 - 1;
  }
  if ( !(unsigned int)CLogState::_MapOnePage(this, a2, (struct _RANGEENTRY *)v12, &pExceptionObject)
    && (pExceptionObject <= 0x1FE0
     || !(unsigned int)CLogState::_MapPageRange(this, a2, (struct _RANGEENTRY *)v12, &pExceptionObject)
     && (pExceptionObject <= 0x1FE0
      || !(unsigned int)CLogState::_MapPageRange(this, a2, (struct _RANGEENTRY *)v12, &pExceptionObject))) )
  {
    CLogState::_MapOnePage(this, a2, (struct _RANGEENTRY *)v12, &pExceptionObject);
  }
}

```

## disassembly

```asm
0x180009178  mov     [rsp-8+arg_0], rbx
0x18000917d  mov     [rsp-8+arg_8], rdi
0x180009182  push    rbp
0x180009183  mov     rbp, rsp
0x180009186  sub     rsp, 40h
0x18000918a  mov     eax, [rdx+4]
0x18000918d  mov     rdi, rdx
0x180009190  add     eax, 18h
0x180009193  mov     [rbp+var_1C], 0
0x18000919a  mov     [rbp+var_14], 0
0x1800091a1  mov     rbx, rcx
0x1800091a4  mov     [rbp+var_4], 0
0x1800091ab  mov     [rbp+pExceptionObject], eax
0x1800091ae  test    r8d, r8d
0x1800091b1  jnz     short loc_1800091C9
0x1800091b3  mov     eax, [rcx+18h]
0x1800091b6  mov     ecx, [rcx+20h]
0x1800091b9  cmp     ecx, eax
0x1800091bb  jbe     short loc_1800091C9
0x1800091bd  cmp     [rdx], ecx
0x1800091bf  jnb     short loc_1800091C9
0x1800091c1  cmp     [rdx], eax
0x1800091c3  jnb     loc_18000927A
0x1800091c9  mov     ecx, [rbx+50h]
0x1800091cc  mov     eax, [rdx]
0x1800091ce  neg     ecx
0x1800091d0  and     ecx, [rdx]
0x1800091d2  sub     eax, ecx
0x1800091d4  mov     [rbp+var_18], ecx
0x1800091d7  mov     ecx, [rbx+1Ch]
0x1800091da  sub     eax, 20h ; ' '
0x1800091dd  cmp     dword ptr [rbx+68h], 0
0x1800091e1  mov     [rbp+var_20], eax
0x1800091e4  mov     [rbp+var_10], ecx
0x1800091e7  mov     [rbp+var_C], 0
0x1800091ef  jz      short loc_180009203
0x1800091f1  mov     eax, [rbx+20h]
0x1800091f4  cmp     eax, [rbx+18h]
0x1800091f7  jbe     short loc_180009203
0x1800091f9  cmp     [rdx], eax
0x1800091fb  jb      short loc_180009203
0x1800091fd  lea     eax, [rcx-1]
0x180009200  mov     [rbp+var_10], eax
0x180009203  lea     r9, [rbp+pExceptionObject]; unsigned int *
0x180009207  mov     rcx, rbx; this
0x18000920a  lea     r8, [rbp+var_20]; struct _RANGEENTRY *
0x18000920e  call    ?_MapOnePage@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z; CLogState::_MapOnePage(CReadMap &,_RANGEENTRY *,ulong *)
0x180009213  test    eax, eax
0x180009215  jnz     short loc_18000926A
0x180009217  cmp     [rbp+pExceptionObject], 1FE0h
0x18000921e  jbe     short loc_180009257
0x180009220  lea     r9, [rbp+pExceptionObject]; unsigned int *
0x180009224  mov     rdx, rdi; struct CReadMap *
0x180009227  lea     r8, [rbp+var_20]; struct _RANGEENTRY *
0x18000922b  mov     rcx, rbx; this
0x18000922e  call    ?_MapPageRange@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z; CLogState::_MapPageRange(CReadMap &,_RANGEENTRY *,ulong *)
0x180009233  test    eax, eax
0x180009235  jnz     short loc_18000926A
0x180009237  cmp     [rbp+pExceptionObject], 1FE0h
0x18000923e  jbe     short loc_180009257
0x180009240  lea     r9, [rbp+pExceptionObject]; unsigned int *
0x180009244  mov     rdx, rdi; struct CReadMap *
0x180009247  lea     r8, [rbp+var_20]; struct _RANGEENTRY *
0x18000924b  mov     rcx, rbx; this
0x18000924e  call    ?_MapPageRange@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z; CLogState::_MapPageRange(CReadMap &,_RANGEENTRY *,ulong *)
0x180009253  test    eax, eax
0x180009255  jnz     short loc_18000926A
0x180009257  lea     r9, [rbp+pExceptionObject]; unsigned int *
0x18000925b  mov     rdx, rdi; struct CReadMap *
0x18000925e  lea     r8, [rbp+var_20]; struct _RANGEENTRY *
0x180009262  mov     rcx, rbx; this
0x180009265  call    ?_MapOnePage@CLogState@@AEAAHAEAVCReadMap@@PEAU_RANGEENTRY@@PEAK@Z; CLogState::_MapOnePage(CReadMap &,_RANGEENTRY *,ulong *)
0x18000926a  mov     rbx, [rsp+40h+arg_0]
0x18000926f  mov     rdi, [rsp+40h+arg_8]
0x180009274  add     rsp, 40h
0x180009278  pop     rbp
0x180009279  retn
0x18000927a  lea     rdx, _TI1K; pThrowInfo
0x180009281  mov     [rbp+pExceptionObject], 0C000103Ah
0x180009288  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000928c  call    _CxxThrowException_0
```
