# CTabRecoveryData::_ReadEntryData(IStream *,ulong,_TRAVEL_LOG_ENTRY_DATA *)

- ea: `0x18022c848`
- end: `0x18022ca5c`
- name: `?_ReadEntryData@CTabRecoveryData@@AEAAJPEAUIStream@@KPEAU_TRAVEL_LOG_ENTRY_DATA@@@Z`
- size: `532`
- prototype: `int(CTabRecoveryData *__hidden this, struct IStream *, unsigned int, struct _TRAVEL_LOG_ENTRY_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180226b50`

## callees

- `0x18022c848`
- `0x18022cd98`
- `0x18022cf18`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x18022ca2b`
- `KERNEL32!GlobalFree` at `0x18022ca40`
- `KERNEL32!GlobalFree` at `0x18022ca2b`
- `KERNEL32!GlobalFree` at `0x18022ca40`
- `SHELL32!__imp_ILFree` at `0x18022ca01`
- `SHELL32!__imp_ILFree` at `0x18022ca01`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18022c864`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18022c864`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18022ca16`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18022ca16`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8a0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8c0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8e0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c900`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c921`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c957`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c977`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c993`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c9af`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8a0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8c0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c8e0`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c900`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c921`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c957`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c977`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c993`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18022c9af`

## pseudocode

```c
__int64 __fastcall CTabRecoveryData::_ReadEntryData(
        CTabRecoveryData *this,
        struct IStream *a2,
        char a3,
        struct _TRAVEL_LOG_ENTRY_DATA *a4)
{
  CTabRecoveryData *v7; // rcx
  HRESULT String; // ebx
  CTabRecoveryData *v9; // rcx
  CTabRecoveryData *v10; // rcx
  CTabRecoveryData *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx

  String = ILLoadFromStreamEx(a2, (LPITEMIDLIST *)a4);
  if ( String < 0 )
    goto LABEL_28;
  String = CTabRecoveryData::_ReadString(v7, a2, (unsigned __int16 **)a4 + 1);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 16, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 20, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 24, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 28, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 40, 0x10u);
  if ( String < 0 )
    goto LABEL_28;
  String = CTabRecoveryData::_ReadHGlobal(v9, a2, (void **)a4 + 7);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 64, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 68, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 72, 4u);
  if ( String < 0 )
    goto LABEL_28;
  String = IStream_Read(a2, (char *)a4 + 32, 4u);
  if ( String < 0 )
    goto LABEL_28;
  if ( (a3 & 1) == 0 )
    *((_DWORD *)a4 + 8) = 0;
  *((_DWORD *)a4 + 9) = 0;
  String = CTabRecoveryData::_ReadHGlobal(v10, a2, (void **)a4 + 10);
  if ( String < 0 || (String = CTabRecoveryData::_ReadHGlobal(v11, a2, (void **)a4 + 11), String < 0) )
  {
LABEL_28:
    if ( *(_QWORD *)a4 )
      ILFree(*(LPITEMIDLIST *)a4);
    v12 = (void *)*((_QWORD *)a4 + 1);
    if ( v12 )
      CoTaskMemFree(v12);
    v13 = (void *)*((_QWORD *)a4 + 7);
    if ( v13 )
      GlobalFree(v13);
    v14 = (void *)*((_QWORD *)a4 + 11);
    if ( v14 )
      GlobalFree(v14);
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18022c848  push    rbx
0x18022c84a  push    rbp
0x18022c84b  push    rsi
0x18022c84c  push    rdi
0x18022c84d  push    r14
0x18022c84f  push    r15
0x18022c851  sub     rsp, 28h
0x18022c855  mov     rsi, rdx
0x18022c858  mov     rdi, r9
0x18022c85b  mov     rcx, rsi; pstm
0x18022c85e  mov     rdx, r9; pidl
0x18022c861  mov     ebp, r8d
0x18022c864  call    cs:__imp_ILLoadFromStreamEx
0x18022c86b  nop     dword ptr [rax+rax+00h]
0x18022c870  mov     ebx, eax
0x18022c872  test    eax, eax
0x18022c874  js      loc_18022C9F9
0x18022c87a  lea     r8, [rdi+8]; unsigned __int16 **
0x18022c87e  mov     rdx, rsi; struct IStream *
0x18022c881  call    ?_ReadString@CTabRecoveryData@@AEAAJPEAUIStream@@PEAPEAG@Z; CTabRecoveryData::_ReadString(IStream *,ushort * *)
0x18022c886  mov     ebx, eax
0x18022c888  test    eax, eax
0x18022c88a  js      loc_18022C9F9
0x18022c890  mov     r15d, 4
0x18022c896  lea     rdx, [rdi+10h]; pv
0x18022c89a  mov     r8d, r15d; cb
0x18022c89d  mov     rcx, rsi; pstm
0x18022c8a0  call    cs:__imp_IStream_Read
0x18022c8a7  nop     dword ptr [rax+rax+00h]
0x18022c8ac  mov     ebx, eax
0x18022c8ae  test    eax, eax
0x18022c8b0  js      loc_18022C9F9
0x18022c8b6  lea     rdx, [rdi+14h]; pv
0x18022c8ba  mov     r8d, r15d; cb
0x18022c8bd  mov     rcx, rsi; pstm
0x18022c8c0  call    cs:__imp_IStream_Read
0x18022c8c7  nop     dword ptr [rax+rax+00h]
0x18022c8cc  mov     ebx, eax
0x18022c8ce  test    eax, eax
0x18022c8d0  js      loc_18022C9F9
0x18022c8d6  lea     rdx, [rdi+18h]; pv
0x18022c8da  mov     r8d, r15d; cb
0x18022c8dd  mov     rcx, rsi; pstm
0x18022c8e0  call    cs:__imp_IStream_Read
0x18022c8e7  nop     dword ptr [rax+rax+00h]
0x18022c8ec  mov     ebx, eax
0x18022c8ee  test    eax, eax
0x18022c8f0  js      loc_18022C9F9
0x18022c8f6  lea     rdx, [rdi+1Ch]; pv
0x18022c8fa  mov     r8d, r15d; cb
0x18022c8fd  mov     rcx, rsi; pstm
0x18022c900  call    cs:__imp_IStream_Read
0x18022c907  nop     dword ptr [rax+rax+00h]
0x18022c90c  mov     ebx, eax
0x18022c90e  test    eax, eax
0x18022c910  js      loc_18022C9F9
0x18022c916  lea     rdx, [rdi+28h]; pv
0x18022c91a  mov     rcx, rsi; pstm
0x18022c91d  lea     r8d, [r15+0Ch]; cb
0x18022c921  call    cs:__imp_IStream_Read
0x18022c928  nop     dword ptr [rax+rax+00h]
0x18022c92d  mov     ebx, eax
0x18022c92f  test    eax, eax
0x18022c931  js      loc_18022C9F9
0x18022c937  lea     r8, [rdi+38h]; void **
0x18022c93b  mov     rdx, rsi; struct IStream *
0x18022c93e  call    ?_ReadHGlobal@CTabRecoveryData@@AEAAJPEAUIStream@@PEAPEAX@Z; CTabRecoveryData::_ReadHGlobal(IStream *,void * *)
0x18022c943  mov     ebx, eax
0x18022c945  test    eax, eax
0x18022c947  js      loc_18022C9F9
0x18022c94d  lea     rdx, [rdi+40h]; pv
0x18022c951  mov     r8d, r15d; cb
0x18022c954  mov     rcx, rsi; pstm
0x18022c957  call    cs:__imp_IStream_Read
0x18022c95e  nop     dword ptr [rax+rax+00h]
0x18022c963  mov     ebx, eax
0x18022c965  test    eax, eax
0x18022c967  js      loc_18022C9F9
0x18022c96d  lea     rdx, [rdi+44h]; pv
0x18022c971  mov     r8d, r15d; cb
0x18022c974  mov     rcx, rsi; pstm
0x18022c977  call    cs:__imp_IStream_Read
0x18022c97e  nop     dword ptr [rax+rax+00h]
0x18022c983  mov     ebx, eax
0x18022c985  test    eax, eax
0x18022c987  js      short loc_18022C9F9
0x18022c989  lea     rdx, [rdi+48h]; pv
0x18022c98d  mov     r8d, r15d; cb
0x18022c990  mov     rcx, rsi; pstm
0x18022c993  call    cs:__imp_IStream_Read
0x18022c99a  nop     dword ptr [rax+rax+00h]
0x18022c99f  mov     ebx, eax
0x18022c9a1  test    eax, eax
0x18022c9a3  js      short loc_18022C9F9
0x18022c9a5  mov     r8d, r15d; cb
0x18022c9a8  lea     rdx, [rdi+20h]; pv
0x18022c9ac  mov     rcx, rsi; pstm
0x18022c9af  call    cs:__imp_IStream_Read
0x18022c9b6  nop     dword ptr [rax+rax+00h]
0x18022c9bb  mov     ebx, eax
0x18022c9bd  test    eax, eax
0x18022c9bf  js      short loc_18022C9F9
0x18022c9c1  test    bpl, 1
0x18022c9c5  jnz     short loc_18022C9CE
0x18022c9c7  mov     dword ptr [rdi+20h], 0
0x18022c9ce  lea     r8, [rdi+50h]; void **
0x18022c9d2  mov     dword ptr [rdi+24h], 0
0x18022c9d9  mov     rdx, rsi; struct IStream *
0x18022c9dc  call    ?_ReadHGlobal@CTabRecoveryData@@AEAAJPEAUIStream@@PEAPEAX@Z; CTabRecoveryData::_ReadHGlobal(IStream *,void * *)
0x18022c9e1  mov     ebx, eax
0x18022c9e3  test    eax, eax
0x18022c9e5  js      short loc_18022C9F9
0x18022c9e7  lea     r8, [rdi+58h]; void **
0x18022c9eb  mov     rdx, rsi; struct IStream *
0x18022c9ee  call    ?_ReadHGlobal@CTabRecoveryData@@AEAAJPEAUIStream@@PEAPEAX@Z; CTabRecoveryData::_ReadHGlobal(IStream *,void * *)
0x18022c9f3  mov     ebx, eax
0x18022c9f5  test    eax, eax
0x18022c9f7  jns     short loc_18022CA4C
0x18022c9f9  mov     rcx, [rdi]; pidl
0x18022c9fc  test    rcx, rcx
0x18022c9ff  jz      short loc_18022CA0D
0x18022ca01  call    cs:__imp_ILFree
0x18022ca08  nop     dword ptr [rax+rax+00h]
0x18022ca0d  mov     rcx, [rdi+8]; pv
0x18022ca11  test    rcx, rcx
0x18022ca14  jz      short loc_18022CA22
0x18022ca16  call    cs:__imp_CoTaskMemFree
0x18022ca1d  nop     dword ptr [rax+rax+00h]
0x18022ca22  mov     rcx, [rdi+38h]; hMem
0x18022ca26  test    rcx, rcx
0x18022ca29  jz      short loc_18022CA37
0x18022ca2b  call    cs:__imp_GlobalFree
0x18022ca32  nop     dword ptr [rax+rax+00h]
0x18022ca37  mov     rcx, [rdi+58h]; hMem
0x18022ca3b  test    rcx, rcx
0x18022ca3e  jz      short loc_18022CA4C
0x18022ca40  call    cs:__imp_GlobalFree
0x18022ca47  nop     dword ptr [rax+rax+00h]
0x18022ca4c  mov     eax, ebx
0x18022ca4e  add     rsp, 28h
0x18022ca52  pop     r15
0x18022ca54  pop     r14
0x18022ca56  pop     rdi
0x18022ca57  pop     rsi
0x18022ca58  pop     rbp
0x18022ca59  pop     rbx
0x18022ca5a  retn
```
