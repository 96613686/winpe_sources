# CUniversalRefresher::XConfigure::AddObjectByTemplate(IWbemServices *,IWbemClassObject *,long,IWbemContext *,IWbemClassObject * *,long *)

- ea: `0x180046a70`
- end: `0x180046c85`
- name: `?AddObjectByTemplate@XConfigure@CUniversalRefresher@@UEAAJPEAUIWbemServices@@PEAUIWbemClassObject@@JPEAUIWbemContext@@PEAPEAU4@PEAJ@Z`
- size: `533`
- prototype: `__int64 __fastcall(CUniversalRefresher::XConfigure *this, IUnknown *, struct IWbemClassObject *, int, struct IWbemContext *, struct IWbemClassObject **, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180037120`
- `0x180046a70`
- `0x180046c90`
- `0x180046ee0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180046abd`
- `wbemcomn!GetMemLogObject` at `0x180046ba6`
- `wbemcomn!GetMemLogObject` at `0x180046bfa`
- `wbemcomn!GetMemLogObject` at `0x180046c26`
- `wbemcomn!GetMemLogObject` at `0x180046abd`
- `wbemcomn!GetMemLogObject` at `0x180046ba6`
- `wbemcomn!GetMemLogObject` at `0x180046bfa`
- `wbemcomn!GetMemLogObject` at `0x180046c26`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180046b1f`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x180046b1f`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180046afc`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x180046afc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046acb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046bb1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c34`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046acb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046bb1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c05`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180046c34`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180046b7b`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x180046b7b`

## pseudocode

```c
__int64 __fastcall CUniversalRefresher::XConfigure::AddObjectByTemplate(
        CUniversalRefresher::XConfigure *this,
        IUnknown *a2,
        struct IWbemClassObject *a3,
        int a4,
        struct IWbemContext *a5,
        struct IWbemClassObject **a6,
        int *a7)
{
  CMemoryLog *v10; // rax
  CWbemRefreshingSvc *v11; // rcx
  int RelPath; // edi
  unsigned __int16 *LPWSTR; // rax
  CWbemRefreshingSvc *v15; // rcx
  __int64 v16; // rdx
  CMemoryLog *v17; // rax
  __int64 v18; // rdx
  CMemoryLog *v19; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v21[72]; // [rsp+40h] [rbp-48h] BYREF

  if ( !a2 || !a3 || !a6 || a4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v16 = 16;
    goto LABEL_28;
  }
  if ( ((__int64)a3[9].lpVtbl->QueryInterface & 3) != 2 )
  {
    v10 = GetMemLogObject();
    CMemoryLog::Write(v10, -2147217400);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v16 = 17;
LABEL_28:
    WPP_SF_d(*((_QWORD *)v11 + 2), v16, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  CVar::CVar((CVar *)v21);
  RelPath = CWbemObject::GetRelPath((CWbemObject *)a3, (struct CVar *)v21);
  if ( RelPath < 0 )
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, RelPath);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v18 = 18;
  }
  else
  {
    LPWSTR = CVar::GetLPWSTR((CVar *)v21);
    RelPath = CUniversalRefresher::XConfigure::AddObjectByPath(this, a2, LPWSTR, 0, a5, a6, a7);
    if ( RelPath < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, RelPath);
    }
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_12;
    }
    v18 = 19;
  }
  WPP_SF_d(*((_QWORD *)v15 + 2), v18, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, (unsigned int)RelPath);
LABEL_12:
  CVar::~CVar((CVar *)v21);
  return (unsigned int)RelPath;
}

```

## disassembly

```asm
0x180046a70  push    rbp
0x180046a72  push    rsi
0x180046a73  push    rdi
0x180046a74  push    r14
0x180046a76  sub     rsp, 68h
0x180046a7a  mov     rdi, r8
0x180046a7d  mov     rbp, rdx
0x180046a80  mov     r14, rcx
0x180046a83  test    rdx, rdx
0x180046a86  jz      loc_180046C26
0x180046a8c  test    r8, r8
0x180046a8f  jz      loc_180046C26
0x180046a95  mov     rsi, [rsp+88h+arg_28]
0x180046a9d  test    rsi, rsi
0x180046aa0  jz      loc_180046C26
0x180046aa6  test    r9d, r9d
0x180046aa9  jnz     loc_180046C26
0x180046aaf  mov     rax, [r8+48h]
0x180046ab3  mov     cl, [rax]
0x180046ab5  and     cl, 3
0x180046ab8  cmp     cl, 2
0x180046abb  jz      short loc_180046AF7
0x180046abd  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046ac3  mov     edx, 80041008h
0x180046ac8  mov     rcx, rax
0x180046acb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046ad1  lea     rax, WPP_GLOBAL_Control
0x180046ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180046adf  cmp     rcx, rax
0x180046ae2  jnz     loc_180046B88
0x180046ae8  mov     eax, 80041008h
0x180046aed  add     rsp, 68h
0x180046af1  pop     r14
0x180046af3  pop     rdi
0x180046af4  pop     rsi
0x180046af5  pop     rbp
0x180046af6  retn
0x180046af7  lea     rcx, [rsp+88h+var_48]
0x180046afc  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x180046b02  nop
0x180046b03  lea     rdx, [rsp+88h+var_48]; struct CVar *
0x180046b08  mov     rcx, rdi; this
0x180046b0b  call    ?GetRelPath@CWbemObject@@QEAAJPEAVCVar@@@Z; CWbemObject::GetRelPath(CVar *)
0x180046b10  mov     edi, eax
0x180046b12  test    eax, eax
0x180046b14  js      loc_180046BA6
0x180046b1a  lea     rcx, [rsp+88h+var_48]
0x180046b1f  call    cs:__imp_?GetLPWSTR@CVar@@QEAAPEAGXZ; CVar::GetLPWSTR(void)
0x180046b25  mov     r8, rax; unsigned __int16 *
0x180046b28  mov     rax, [rsp+88h+arg_30]
0x180046b30  mov     [rsp+88h+var_58], rax; int *
0x180046b35  mov     [rsp+88h+var_60], rsi; struct IWbemClassObject **
0x180046b3a  mov     rax, [rsp+88h+arg_20]
0x180046b42  mov     [rsp+88h+var_68], rax; struct IWbemContext *
0x180046b47  xor     r9d, r9d; int
0x180046b4a  mov     rdx, rbp; struct IWbemServices *
0x180046b4d  mov     rcx, r14; this
0x180046b50  call    ?AddObjectByPath@XConfigure@CUniversalRefresher@@UEAAJPEAUIWbemServices@@PEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@PEAJ@Z; CUniversalRefresher::XConfigure::AddObjectByPath(IWbemServices *,ushort const *,long,IWbemContext *,IWbemClassObject * *,long *)
0x180046b55  mov     edi, eax
0x180046b57  test    eax, eax
0x180046b59  js      loc_180046BFA
0x180046b5f  lea     rax, WPP_GLOBAL_Control
0x180046b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b6d  cmp     rcx, rax
0x180046b70  jnz     loc_180046C10
0x180046b76  lea     rcx, [rsp+88h+var_48]
0x180046b7b  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x180046b81  mov     eax, edi
0x180046b83  jmp     loc_180046AED
0x180046b88  test    byte ptr [rcx+1Ch], 1
0x180046b8c  jz      loc_180046AE8
0x180046b92  cmp     byte ptr [rcx+19h], 2
0x180046b96  jb      loc_180046AE8
0x180046b9c  mov     edx, 11h
0x180046ba1  jmp     loc_180046C6A
0x180046ba6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046bac  mov     edx, edi
0x180046bae  mov     rcx, rax
0x180046bb1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046bb7  lea     rax, WPP_GLOBAL_Control
0x180046bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bc5  cmp     rcx, rax
0x180046bc8  jz      short loc_180046B76
0x180046bca  test    byte ptr [rcx+1Ch], 1
0x180046bce  jz      short loc_180046B76
0x180046bd0  cmp     byte ptr [rcx+19h], 2
0x180046bd4  jb      short loc_180046B76
0x180046bd6  mov     edx, 12h
0x180046bdb  jmp     short loc_180046BE2
0x180046bdd  mov     edx, 13h
0x180046be2  mov     r9d, edi
0x180046be5  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180046bec  mov     rcx, [rcx+10h]
0x180046bf0  call    WPP_SF_d
0x180046bf5  jmp     loc_180046B76
0x180046bfa  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046c00  mov     edx, edi
0x180046c02  mov     rcx, rax
0x180046c05  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046c0b  jmp     loc_180046B5F
0x180046c10  test    byte ptr [rcx+1Ch], 1
0x180046c14  jz      loc_180046B76
0x180046c1a  cmp     byte ptr [rcx+19h], 2
0x180046c1e  jb      loc_180046B76
0x180046c24  jmp     short loc_180046BDD
0x180046c26  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180046c2c  mov     edx, 80041008h
0x180046c31  mov     rcx, rax
0x180046c34  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180046c3a  lea     rax, WPP_GLOBAL_Control
0x180046c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c48  cmp     rcx, rax
0x180046c4b  jz      loc_180046AE8
0x180046c51  test    byte ptr [rcx+1Ch], 1
0x180046c55  jz      loc_180046AE8
0x180046c5b  cmp     byte ptr [rcx+19h], 2
0x180046c5f  jb      loc_180046AE8
0x180046c65  mov     edx, 10h
0x180046c6a  mov     r9d, 80041008h
0x180046c70  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180046c77  mov     rcx, [rcx+10h]
0x180046c7b  call    WPP_SF_d
0x180046c80  jmp     loc_180046AE8
```
