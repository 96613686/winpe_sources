# DRMAcquireIssuanceLicenseTemplate

- ea: `0x18001e3e0`
- end: `0x18001e535`
- name: `DRMAcquireIssuanceLicenseTemplate`
- size: `341`
- prototype: `HRESULT __stdcall(DRMHSESSION hClient, UINT uFlags, void *pvReserved, UINT cTemplates, PWSTR *pwszTemplateIds, PWSTR wszUrl, void *pvContext)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017acc`
- `0x180018650`

## callees

- `0x180001284`
- `0x18000420c`
- `0x1800046c8`
- `0x18001d914`
- `0x18001e3e0`
- `0x18001fa40`
- `0x18001ff90`
- `0x180022730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e488`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e480`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e488`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e46c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e46c`

## string_xrefs

- `0x18001e507`: `[msdrm]:AcquireILTemplates FAILED %x`

## pseudocode

```c
HRESULT __stdcall DRMAcquireIssuanceLicenseTemplate(
        DRMHSESSION hClient,
        UINT uFlags,
        void *pvReserved,
        UINT cTemplates,
        PWSTR *pwszTemplateIds,
        PWSTR wszUrl,
        void *pvContext)
{
  HRESULT v9; // ebx
  char valid; // al
  CHandleTable *v11; // rcx
  void *v12; // rdi
  CDRMCBase *v13; // rsi
  __int64 v14; // rbx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  int (*Callback)(enum _DRM_STATUS_MSG, int, void *, void *); // r8
  int v17; // eax
  void *Block; // [rsp+30h] [rbp-38h] BYREF

  if ( !hClient )
    return -2147024809;
  valid = DRMIsValidStringT<unsigned short>(wszUrl, 0, pvReserved, cTemplates);
  if ( (uFlags & 4) == 0 && (!valid || (uFlags & 2) == 0) )
    return -2147024809;
  Block = 0;
  if ( CHandleTable::Get(v11, hClient, (struct DRMCInt **)&Block) < 0 )
    return -2147024890;
  v12 = Block;
  if ( !Block )
    return -2147024890;
  if ( *(_DWORD *)Block == 2 )
  {
    v14 = *((_QWORD *)Block + 1);
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 88));
    v15 = (struct _RTL_CRITICAL_SECTION *)(v14 + 88);
    if ( *(_DWORD *)(v14 + 136) == -1 )
    {
      v13 = 0;
      LeaveCriticalSection(v15);
    }
    else
    {
      LeaveCriticalSection(v15);
      v13 = (CDRMCBase *)*((_QWORD *)v12 + 1);
    }
  }
  else
  {
    v13 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v12 + 4, 0xFFFFFFFF) == 1 )
    operator delete(v12);
  if ( !v13 )
    return -2147024890;
  if ( (uFlags & 4) != 0 )
  {
    v9 = 0;
    if ( !(unsigned int)CDRMCBase::IsThreadAlive(v13, 3u) )
      return v9;
  }
  else if ( (unsigned int)CDRMCBase::IsThreadAlive(v13, 3u) )
  {
    return -2147168456;
  }
  Callback = CDRMClient::GetCallback(v13);
  v17 = AcquireILTemplates(hClient, uFlags, Callback, wszUrl, pvContext);
  v9 = v17;
  if ( v17 < 0 )
    _RTLTRACE("[msdrm]:AcquireILTemplates FAILED %x", v17);
  return v9;
}

```

## disassembly

```asm
0x18001e3e0  mov     [rsp+arg_8], rbx
0x18001e3e5  mov     [rsp+arg_10], rbp
0x18001e3ea  push    rsi
0x18001e3eb  push    rdi
0x18001e3ec  push    r12
0x18001e3ee  push    r14
0x18001e3f0  push    r15
0x18001e3f2  sub     rsp, 40h
0x18001e3f6  mov     r15d, edx
0x18001e3f9  mov     r12d, ecx
0x18001e3fc  test    ecx, ecx
0x18001e3fe  jnz     short loc_18001E40A
0x18001e400  mov     ebx, 80070057h
0x18001e405  jmp     loc_18001E51A
0x18001e40a  mov     rcx, [rsp+68h+wszUrl]
0x18001e412  xor     edx, edx
0x18001e414  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x18001e419  mov     r14d, r15d
0x18001e41c  and     r14d, 4
0x18001e420  jnz     short loc_18001E42C
0x18001e422  test    al, al
0x18001e424  jz      short loc_18001E400
0x18001e426  test    r15b, 2
0x18001e42a  jz      short loc_18001E400
0x18001e42c  lea     r8, [rsp+68h+Block]; struct DRMCInt **
0x18001e431  mov     [rsp+68h+Block], 0
0x18001e43a  mov     edx, r12d; unsigned int
0x18001e43d  call    ?Get@CHandleTable@@QEAAJKPEAPEAUDRMCInt@@@Z; CHandleTable::Get(ulong,DRMCInt * *)
0x18001e442  test    eax, eax
0x18001e444  js      loc_18001E515
0x18001e44a  mov     rdi, [rsp+68h+Block]
0x18001e44f  test    rdi, rdi
0x18001e452  jz      loc_18001E515
0x18001e458  cmp     dword ptr [rdi], 2
0x18001e45b  jz      short loc_18001E461
0x18001e45d  xor     esi, esi
0x18001e45f  jmp     short loc_18001E492
0x18001e461  mov     rbx, [rdi+8]
0x18001e465  lea     rbp, [rbx+58h]
0x18001e469  mov     rcx, rbp; lpCriticalSection
0x18001e46c  call    cs:__imp_EnterCriticalSection
0x18001e472  cmp     dword ptr [rbx+88h], 0FFFFFFFFh
0x18001e479  mov     rcx, rbp; lpCriticalSection
0x18001e47c  jnz     short loc_18001E488
0x18001e47e  xor     esi, esi
0x18001e480  call    cs:__imp_LeaveCriticalSection
0x18001e486  jmp     short loc_18001E492
0x18001e488  call    cs:__imp_LeaveCriticalSection
0x18001e48e  mov     rsi, [rdi+8]
0x18001e492  or      eax, 0FFFFFFFFh
0x18001e495  lock xadd [rdi+10h], eax
0x18001e49a  cmp     eax, 1
0x18001e49d  jnz     short loc_18001E4A7
0x18001e49f  mov     rcx, rdi; Block
0x18001e4a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001e4a7  test    rsi, rsi
0x18001e4aa  jz      short loc_18001E515
0x18001e4ac  mov     edx, 3; unsigned int
0x18001e4b1  mov     rcx, rsi; this
0x18001e4b4  test    r14d, r14d
0x18001e4b7  jnz     short loc_18001E4C9
0x18001e4b9  call    ?IsThreadAlive@CDRMCBase@@QEAAHI@Z; CDRMCBase::IsThreadAlive(uint)
0x18001e4be  test    eax, eax
0x18001e4c0  jz      short loc_18001E4D4
0x18001e4c2  mov     ebx, 8004CF38h
0x18001e4c7  jmp     short loc_18001E51A
0x18001e4c9  xor     ebx, ebx
0x18001e4cb  call    ?IsThreadAlive@CDRMCBase@@QEAAHI@Z; CDRMCBase::IsThreadAlive(uint)
0x18001e4d0  test    eax, eax
0x18001e4d2  jz      short loc_18001E51A
0x18001e4d4  mov     rcx, rsi; this
0x18001e4d7  call    ?GetCallback@CDRMClient@@QEAAP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZXZ; CDRMClient::GetCallback(void)
0x18001e4dc  mov     r9, [rsp+68h+wszUrl]; unsigned __int16 *
0x18001e4e4  mov     r8, rax; int (*)(enum _DRM_STATUS_MSG, int, void *, void *)
0x18001e4e7  mov     rax, [rsp+68h+pvContext]
0x18001e4ef  mov     edx, r15d; unsigned int
0x18001e4f2  mov     ecx, r12d; unsigned int
0x18001e4f5  mov     [rsp+68h+var_48], rax; void *
0x18001e4fa  call    ?AcquireILTemplates@@YAJKIP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZPEAG1@Z; AcquireILTemplates(ulong,uint,long (*)(_DRM_STATUS_MSG,long,void *,void *),ushort *,void *)
0x18001e4ff  mov     ebx, eax
0x18001e501  test    eax, eax
0x18001e503  jns     short loc_18001E51A
0x18001e505  mov     edx, eax
0x18001e507  lea     rcx, aMsdrmAcquireil; "[msdrm]:AcquireILTemplates FAILED %x"
0x18001e50e  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001e513  jmp     short loc_18001E51A
0x18001e515  mov     ebx, 80070006h
0x18001e51a  lea     r11, [rsp+68h+var_28]
0x18001e51f  mov     eax, ebx
0x18001e521  mov     rbx, [r11+38h]
0x18001e525  mov     rbp, [r11+40h]
0x18001e529  mov     rsp, r11
0x18001e52c  pop     r15
0x18001e52e  pop     r14
0x18001e530  pop     r12
0x18001e532  pop     rdi
0x18001e533  pop     rsi
0x18001e534  retn
```
