# CUniversalRefresher::AddRefresher(IWbemRefresher *,long,long *)

- ea: `0x1800879ac`
- end: `0x180087b9a`
- name: `?AddRefresher@CUniversalRefresher@@IEAAJPEAUIWbemRefresher@@JPEAJ@Z`
- size: `494`
- prototype: `__int64 __fastcall(CUniversalRefresher *__hidden this, struct IWbemRefresher *, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180087ba0`

## callees

- `0x180037120`
- `0x1800700c8`
- `0x180070868`
- `0x18007212c`
- `0x1800879ac`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180087a27`
- `wbemcomn!GetMemLogObject` at `0x180087ae2`
- `wbemcomn!GetMemLogObject` at `0x180087b3f`
- `wbemcomn!GetMemLogObject` at `0x180087a27`
- `wbemcomn!GetMemLogObject` at `0x180087ae2`
- `wbemcomn!GetMemLogObject` at `0x180087b3f`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180087a93`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180087a93`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180087a86`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180087a86`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087a37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087af2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087b4f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087a37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087af2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180087b4f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800879d4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800879d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUniversalRefresher::AddRefresher(
        CUniversalRefresher *this,
        struct IWbemRefresher *a2,
        int a3,
        int *a4)
{
  CUniversalRefresher::CNestedRefresher *v7; // rax
  __int64 v8; // rbx
  CUniversalRefresher::CNestedRefresher *v9; // rdx
  CMemoryLog *v10; // rax
  unsigned int v11; // ebx
  unsigned int v12; // edx
  CWbemRefreshingSvc *v13; // rcx
  __int64 v14; // rdx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v16; // rax
  CUniversalRefresher::CNestedRefresher *v18; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 && !a3 )
  {
    v7 = (CUniversalRefresher::CNestedRefresher *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v8 = (__int64)v7;
    v18 = v7;
    if ( v7 )
    {
      *(_QWORD *)v7 = a2;
      ((void (__fastcall *)(struct IWbemRefresher *))a2->lpVtbl->AddRef)(a2);
      *(_DWORD *)(v8 + 8) = _InterlockedIncrement(&CUniversalRefresher::mstatic_lLastId);
    }
    else
    {
      v8 = 0;
    }
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v18, v8);
    v9 = v18;
    if ( v18 )
    {
      if ( a4 )
        *a4 = *((_DWORD *)v18 + 2);
      if ( !CFlexArray::Add((CUniversalRefresher *)((char *)this + 320), v9)
        && CFlexArray::Size((CUniversalRefresher *)((char *)this + 320)) )
      {
        std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v18);
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 0);
        }
        v11 = 0;
        goto LABEL_25;
      }
      MemLogObject = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_25:
        std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(
          &v18,
          v12);
        return v11;
      }
      v14 = 90;
    }
    else
    {
      v10 = GetMemLogObject();
      v11 = -2147217402;
      CMemoryLog::Write(v10, -2147217402);
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v14 = 89;
    }
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749894LL);
    goto LABEL_25;
  }
  v16 = GetMemLogObject();
  v11 = -2147217400;
  CMemoryLog::Write(v16, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids, 2147749896LL);
  }
  return v11;
}

```

## disassembly

```asm
0x1800879ac  push    rbx
0x1800879ae  push    rbp
0x1800879af  push    rsi
0x1800879b0  push    rdi
0x1800879b1  sub     rsp, 28h
0x1800879b5  mov     rdi, r9
0x1800879b8  mov     rsi, rdx
0x1800879bb  mov     rbp, rcx
0x1800879be  test    rdx, rdx
0x1800879c1  jz      loc_180087B3F
0x1800879c7  test    r8d, r8d
0x1800879ca  jnz     loc_180087B3F
0x1800879d0  lea     ecx, [r8+10h]
0x1800879d4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800879da  mov     rbx, rax
0x1800879dd  mov     [rsp+48h+arg_8], rax
0x1800879e2  test    rax, rax
0x1800879e5  jz      short loc_180087A0D
0x1800879e7  mov     [rax], rsi
0x1800879ea  mov     rax, [rsi]
0x1800879ed  mov     rcx, rsi
0x1800879f0  mov     rax, [rax+8]
0x1800879f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800879f9  mov     eax, 1
0x1800879fe  lock xadd cs:?mstatic_lLastId@CUniversalRefresher@@1JA, eax; long CUniversalRefresher::mstatic_lLastId
0x180087a06  inc     eax
0x180087a08  mov     [rbx+8], eax
0x180087a0b  jmp     short loc_180087A0F
0x180087a0d  xor     ebx, ebx
0x180087a0f  mov     rdx, rbx
0x180087a12  lea     rcx, [rsp+48h+arg_8]
0x180087a17  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180087a1c  nop
0x180087a1d  mov     rdx, [rsp+48h+arg_8]
0x180087a22  test    rdx, rdx
0x180087a25  jnz     short loc_180087A72
0x180087a27  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180087a2d  mov     ebx, 80041006h
0x180087a32  mov     edx, ebx
0x180087a34  mov     rcx, rax
0x180087a37  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087a3d  lea     rax, WPP_GLOBAL_Control
0x180087a44  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a4b  cmp     rcx, rax
0x180087a4e  jz      loc_180087B33
0x180087a54  test    byte ptr [rcx+1Ch], 1
0x180087a58  jz      loc_180087B33
0x180087a5e  cmp     byte ptr [rcx+19h], 2
0x180087a62  jb      loc_180087B33
0x180087a68  mov     edx, 59h ; 'Y'
0x180087a6d  jmp     loc_180087B1C
0x180087a72  test    rdi, rdi
0x180087a75  jz      short loc_180087A7C
0x180087a77  mov     eax, [rdx+8]
0x180087a7a  mov     [rdi], eax
0x180087a7c  lea     rbx, [rbp+140h]
0x180087a83  mov     rcx, rbx
0x180087a86  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180087a8c  test    eax, eax
0x180087a8e  jnz     short loc_180087AE2
0x180087a90  mov     rcx, rbx
0x180087a93  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180087a99  test    eax, eax
0x180087a9b  jz      short loc_180087AE2
0x180087a9d  lea     rcx, [rsp+48h+arg_8]
0x180087aa2  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180087aa7  lea     rax, WPP_GLOBAL_Control
0x180087aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180087ab5  cmp     rcx, rax
0x180087ab8  jz      short loc_180087ADE
0x180087aba  test    byte ptr [rcx+1Ch], 1
0x180087abe  jz      short loc_180087ADE
0x180087ac0  cmp     byte ptr [rcx+19h], 2
0x180087ac4  jb      short loc_180087ADE
0x180087ac6  mov     edx, 5Bh ; '['
0x180087acb  xor     r9d, r9d
0x180087ace  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087ad5  mov     rcx, [rcx+10h]
0x180087ad9  call    WPP_SF_d
0x180087ade  xor     ebx, ebx
0x180087ae0  jmp     short loc_180087B33
0x180087ae2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180087ae8  mov     ebx, 80041006h
0x180087aed  mov     edx, ebx
0x180087aef  mov     rcx, rax
0x180087af2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087af8  lea     rax, WPP_GLOBAL_Control
0x180087aff  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b06  cmp     rcx, rax
0x180087b09  jz      short loc_180087B33
0x180087b0b  test    byte ptr [rcx+1Ch], 1
0x180087b0f  jz      short loc_180087B33
0x180087b11  cmp     byte ptr [rcx+19h], 2
0x180087b15  jb      short loc_180087B33
0x180087b17  mov     edx, 5Ah ; 'Z'
0x180087b1c  mov     r9d, 80041006h
0x180087b22  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087b29  mov     rcx, [rcx+10h]
0x180087b2d  call    WPP_SF_d
0x180087b32  nop
0x180087b33  lea     rcx, [rsp+48h+arg_8]
0x180087b38  call    ??1?$unique_ptr@VCNestedRefresher@CUniversalRefresher@@U?$default_delete@VCNestedRefresher@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(void)
0x180087b3d  jmp     short loc_180087B8F
0x180087b3f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180087b45  mov     ebx, 80041008h
0x180087b4a  mov     edx, ebx
0x180087b4c  mov     rcx, rax
0x180087b4f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180087b55  lea     rax, WPP_GLOBAL_Control
0x180087b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180087b63  cmp     rcx, rax
0x180087b66  jz      short loc_180087B8F
0x180087b68  test    byte ptr [rcx+1Ch], 1
0x180087b6c  jz      short loc_180087B8F
0x180087b6e  cmp     byte ptr [rcx+19h], 2
0x180087b72  jb      short loc_180087B8F
0x180087b74  mov     edx, 58h ; 'X'
0x180087b79  mov     r9d, 80041008h
0x180087b7f  lea     r8, WPP_1f3c046fddbb3be76487e93b3f0645fb_Traceguids
0x180087b86  mov     rcx, [rcx+10h]
0x180087b8a  call    WPP_SF_d
0x180087b8f  mov     eax, ebx
0x180087b91  add     rsp, 28h
0x180087b95  pop     rdi
0x180087b96  pop     rsi
0x180087b97  pop     rbp
0x180087b98  pop     rbx
0x180087b99  retn
```
