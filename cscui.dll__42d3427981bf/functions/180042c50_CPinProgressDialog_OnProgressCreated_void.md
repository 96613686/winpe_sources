# CPinProgressDialog::_OnProgressCreated(void)

- ea: `0x180042c50`
- end: `0x180042d31`
- name: `?_OnProgressCreated@CPinProgressDialog@@AEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(CPinProgressDialog *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180042dc0`

## callees

- `0x180006500`
- `0x180010ff4`
- `0x18001101c`
- `0x180042c50`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThread` at `0x180042ca7`
- `SHLWAPI!__imp_SHCreateThread` at `0x180042ca7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042cbd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180042cbd`

## pseudocode

```c
__int64 __fastcall CPinProgressDialog::_OnProgressCreated(CPinProgressDialog *this)
{
  unsigned int v2; // edi
  UstCommon::CImpersonator *v3; // rcx

  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
  }
  v2 = 0;
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  if ( !SHCreateThread(CPinProgressDialog::_WorkerThreadProc, this, 0x18u, 0) )
  {
    v2 = -2147467259;
    SetEvent(*((HANDLE *)this + 30));
    CRefCounted::ReleaseReference(this);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids);
        v3 = WPP_GLOBAL_Control;
      }
      if ( v3 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)v3 + 2), 28, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids, 2147500037LL);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180042c50  mov     [rsp+arg_0], rbx
0x180042c55  mov     [rsp+arg_8], rsi
0x180042c5a  push    rdi
0x180042c5b  sub     rsp, 20h
0x180042c5f  mov     rbx, rcx
0x180042c62  mov     rcx, cs:WPP_GLOBAL_Control
0x180042c69  lea     rsi, WPP_GLOBAL_Control
0x180042c70  cmp     rcx, rsi
0x180042c73  jz      short loc_180042C90
0x180042c75  test    byte ptr [rcx+1Ch], 40h
0x180042c79  jz      short loc_180042C90
0x180042c7b  mov     rcx, [rcx+10h]
0x180042c7f  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042c86  mov     edx, 1Ah
0x180042c8b  call    WPP_SF_
0x180042c90  xor     edi, edi
0x180042c92  lock inc dword ptr [rbx+8]
0x180042c96  xor     r9d, r9d; pfnCallback
0x180042c99  lea     r8d, [rdi+18h]; flags
0x180042c9d  mov     rdx, rbx; pData
0x180042ca0  lea     rcx, ?_WorkerThreadProc@CPinProgressDialog@@CAKPEAX@Z; pfnThreadProc
0x180042ca7  call    cs:__imp_SHCreateThread
0x180042cad  test    eax, eax
0x180042caf  jnz     short loc_180042D1F
0x180042cb1  mov     rcx, [rbx+0F0h]; hEvent
0x180042cb8  mov     edi, 80004005h
0x180042cbd  call    cs:__imp_SetEvent
0x180042cc3  mov     rcx, rbx; this
0x180042cc6  call    ?ReleaseReference@CRefCounted@@QEAAXXZ; CRefCounted::ReleaseReference(void)
0x180042ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180042cd2  cmp     rcx, rsi
0x180042cd5  jz      short loc_180042D1F
0x180042cd7  test    byte ptr [rcx+1Ch], 2
0x180042cdb  jz      short loc_180042CF9
0x180042cdd  mov     rcx, [rcx+10h]
0x180042ce1  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042ce8  mov     edx, 1Bh
0x180042ced  call    WPP_SF_
0x180042cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180042cf9  cmp     rcx, rsi
0x180042cfc  jz      short loc_180042D1F
0x180042cfe  test    byte ptr [rcx+1Ch], 2
0x180042d02  jz      short loc_180042D1F
0x180042d04  mov     rcx, [rcx+10h]
0x180042d08  lea     r8, WPP_5a0e831feac3327f8ebf4faefd7725d1_Traceguids
0x180042d0f  mov     edx, 1Ch
0x180042d14  mov     r9d, 80004005h
0x180042d1a  call    WPP_SF_d
0x180042d1f  mov     rbx, [rsp+28h+arg_0]
0x180042d24  mov     eax, edi
0x180042d26  mov     rsi, [rsp+28h+arg_8]
0x180042d2b  add     rsp, 20h
0x180042d2f  pop     rdi
0x180042d30  retn
```
