# CWbemRefreshingSvc::SetServiceData(ushort *,ushort *)

- ea: `0x180063160`
- end: `0x1800632b9`
- name: `?SetServiceData@CWbemRefreshingSvc@@MEAAJPEAG0@Z`
- size: `345`
- prototype: `int(CWbemRefreshingSvc *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180063150`

## callees

- `0x180037120`
- `0x180063160`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800631d0`
- `wbemcomn!GetMemLogObject` at `0x180063201`
- `wbemcomn!GetMemLogObject` at `0x180063243`
- `wbemcomn!GetMemLogObject` at `0x1800631d0`
- `wbemcomn!GetMemLogObject` at `0x180063201`
- `wbemcomn!GetMemLogObject` at `0x180063243`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800631e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063211`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063253`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800631e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063211`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180063253`
- `OLEAUT32!__imp_SysAllocString` at `0x18006318f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800631a5`
- `OLEAUT32!__imp_SysAllocString` at `0x18006318f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800631a5`

## pseudocode

```c
__int64 __fastcall CWbemRefreshingSvc::SetServiceData(
        CWbemRefreshingSvc *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  BSTR v5; // rax
  CMemoryLog *v7; // rax
  unsigned int v8; // ebx
  CWbemRefreshingSvc *v9; // rcx
  CMemoryLog *MemLogObject; // rax
  __int64 v11; // rdx
  __int64 v12; // r9
  CMemoryLog *v13; // rax

  if ( !*((_QWORD *)this + 4) )
  {
    MemLogObject = GetMemLogObject();
    v8 = -2147217407;
    CMemoryLog::Write(MemLogObject, -2147217407);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 48;
    v12 = 2147749889LL;
    goto LABEL_24;
  }
  if ( !a2 || !a3 )
  {
    v7 = GetMemLogObject();
    v8 = -2147217400;
    CMemoryLog::Write(v7, -2147217400);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v8;
    }
    v11 = 49;
    v12 = 2147749896LL;
    goto LABEL_24;
  }
  if ( !*((_QWORD *)this + 5) )
    *((_QWORD *)this + 5) = SysAllocString(a2);
  v5 = (BSTR)*((_QWORD *)this + 6);
  if ( !v5 )
  {
    v5 = SysAllocString(a3);
    *((_QWORD *)this + 6) = v5;
  }
  if ( *((_QWORD *)this + 5) && v5 )
    return 0;
  v13 = GetMemLogObject();
  v8 = -2147217402;
  CMemoryLog::Write(v13, -2147217402);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v11 = 50;
    v12 = 2147749894LL;
LABEL_24:
    WPP_SF_d(*((_QWORD *)v9 + 2), v11, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids, v12);
  }
  return v8;
}

```

## disassembly

```asm
0x180063160  mov     [rsp+arg_0], rbx
0x180063165  push    rdi
0x180063166  sub     rsp, 20h
0x18006316a  cmp     qword ptr [rcx+20h], 0
0x18006316f  mov     rdi, r8
0x180063172  mov     rbx, rcx
0x180063175  jz      loc_180063201
0x18006317b  test    rdx, rdx
0x18006317e  jz      short loc_1800631D0
0x180063180  test    r8, r8
0x180063183  jz      short loc_1800631D0
0x180063185  cmp     qword ptr [rcx+28h], 0
0x18006318a  jnz     short loc_180063199
0x18006318c  mov     rcx, rdx; psz
0x18006318f  call    cs:__imp_SysAllocString
0x180063195  mov     [rbx+28h], rax
0x180063199  mov     rax, [rbx+30h]
0x18006319d  test    rax, rax
0x1800631a0  jnz     short loc_1800631AF
0x1800631a2  mov     rcx, rdi; psz
0x1800631a5  call    cs:__imp_SysAllocString
0x1800631ab  mov     [rbx+30h], rax
0x1800631af  cmp     qword ptr [rbx+28h], 0
0x1800631b4  jz      loc_180063243
0x1800631ba  test    rax, rax
0x1800631bd  jz      loc_180063243
0x1800631c3  xor     eax, eax
0x1800631c5  mov     rbx, [rsp+28h+arg_0]
0x1800631ca  add     rsp, 20h
0x1800631ce  pop     rdi
0x1800631cf  retn
0x1800631d0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800631d6  mov     ebx, 80041008h
0x1800631db  mov     rcx, rax
0x1800631de  mov     edx, ebx
0x1800631e0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800631e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631ed  lea     rax, WPP_GLOBAL_Control
0x1800631f4  cmp     rcx, rax
0x1800631f7  jnz     loc_180063285
0x1800631fd  mov     eax, ebx
0x1800631ff  jmp     short loc_1800631C5
0x180063201  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180063207  mov     ebx, 80041001h
0x18006320c  mov     rcx, rax
0x18006320f  mov     edx, ebx
0x180063211  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180063217  mov     rcx, cs:WPP_GLOBAL_Control
0x18006321e  lea     rax, WPP_GLOBAL_Control
0x180063225  cmp     rcx, rax
0x180063228  jz      short loc_1800631FD
0x18006322a  test    byte ptr [rcx+1Ch], 1
0x18006322e  jz      short loc_1800631FD
0x180063230  cmp     byte ptr [rcx+19h], 2
0x180063234  jb      short loc_1800631FD
0x180063236  mov     edx, 30h ; '0'
0x18006323b  mov     r9d, 80041001h
0x180063241  jmp     short loc_1800632A4
0x180063243  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180063249  mov     ebx, 80041006h
0x18006324e  mov     rcx, rax
0x180063251  mov     edx, ebx
0x180063253  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180063259  mov     rcx, cs:WPP_GLOBAL_Control
0x180063260  lea     rax, WPP_GLOBAL_Control
0x180063267  cmp     rcx, rax
0x18006326a  jz      short loc_1800631FD
0x18006326c  test    byte ptr [rcx+1Ch], 1
0x180063270  jz      short loc_1800631FD
0x180063272  cmp     byte ptr [rcx+19h], 2
0x180063276  jb      short loc_1800631FD
0x180063278  mov     edx, 32h ; '2'
0x18006327d  mov     r9d, 80041006h
0x180063283  jmp     short loc_1800632A4
0x180063285  test    byte ptr [rcx+1Ch], 1
0x180063289  jz      loc_1800631FD
0x18006328f  cmp     byte ptr [rcx+19h], 2
0x180063293  jb      loc_1800631FD
0x180063299  mov     edx, 31h ; '1'
0x18006329e  mov     r9d, 80041008h
0x1800632a4  mov     rcx, [rcx+10h]
0x1800632a8  lea     r8, WPP_ccade184005d30f1287a0c391cfeefa4_Traceguids
0x1800632af  call    WPP_SF_d
0x1800632b4  jmp     loc_1800631FD
```
