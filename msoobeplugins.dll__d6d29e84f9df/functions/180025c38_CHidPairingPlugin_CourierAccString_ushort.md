# CHidPairingPlugin::_CourierAccString(ushort)

- ea: `0x180025c38`
- end: `0x180025d39`
- name: `?_CourierAccString@CHidPairingPlugin@@AEAAJG@Z`
- size: `257`
- prototype: `__int64 __fastcall(CHidPairingPlugin *__hidden this, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180026a60`

## callees

- `0x18000ac48`
- `0x18000b358`
- `0x180025c38`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025ceb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025ceb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025d05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025d05`

## string_xrefs

- `0x180025d16`: `Ignoring request for HidAcc string-- Acc Task is not running.`

## pseudocode

```c
__int64 __fastcall CHidPairingPlugin::_CourierAccString(CHidPairingPlugin *this, __int64 a2)
{
  int Error; // ebx
  __int64 v4; // rcx
  __int64 v5; // rdi
  int v6; // ebx
  const wchar_t *v7; // rsi
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  size_t v10; // r9
  __int64 v12; // [rsp+20h] [rbp-28h]
  int v13; // [rsp+50h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  Error = 0;
  if ( *((_BYTE *)this + 664) )
  {
    v4 = *((_QWORD *)this + 82);
    if ( v4 )
    {
      pv = 0;
      v13 = 0;
      Error = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v4 + 88LL))(v4, a2, &pv, &v13);
      if ( Error >= 0 )
      {
        v5 = *((_QWORD *)this + 81);
        v6 = v13;
        v7 = (const wchar_t *)pv;
        CoTaskMemFree(*(LPVOID *)(v5 + 624));
        *(_QWORD *)(v5 + 624) = 0;
        *(_DWORD *)(v5 + 632) = v6;
        if ( !v7 )
          goto LABEL_17;
        v10 = -1;
        do
          ++v10;
        while ( v7[v10] );
        Error = _AllocStringWorker<CTCoAllocPolicy>(v9, v8, v7, v10, v12, (void **)(v5 + 624));
        if ( Error >= 0 )
        {
LABEL_17:
          if ( SetEvent(*(HANDLE *)(v5 + 616)) )
            Error = 0;
          else
            Error = ResultFromKnownLastError();
        }
        CoTaskMemFree(pv);
      }
    }
    else
    {
      UnattendLogW(0, L"Ignoring request for HidAcc string-- No Acc Callback.");
    }
  }
  else
  {
    UnattendLogW(0, L"Ignoring request for HidAcc string-- Acc Task is not running.");
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180025c38  mov     r11, rsp
0x180025c3b  mov     [r11+10h], rbx
0x180025c3f  mov     [r11+20h], rbp
0x180025c43  push    rsi
0x180025c44  push    rdi
0x180025c45  push    r14
0x180025c47  sub     rsp, 30h
0x180025c4b  xor     ebp, ebp
0x180025c4d  mov     rdi, rcx
0x180025c50  mov     ebx, ebp
0x180025c52  cmp     [rcx+298h], bpl
0x180025c59  jz      loc_180025D16
0x180025c5f  mov     rcx, [rcx+290h]
0x180025c66  test    rcx, rcx
0x180025c69  jz      loc_180025D0D
0x180025c6f  mov     [r11+18h], rbp
0x180025c73  lea     r9, [r11+8]
0x180025c77  mov     [rsp+48h+arg_0], ebp
0x180025c7b  lea     r8, [r11+18h]
0x180025c7f  mov     rax, [rcx]
0x180025c82  mov     rax, [rax+58h]
0x180025c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c8b  mov     ebx, eax
0x180025c8d  test    eax, eax
0x180025c8f  js      loc_180025D24
0x180025c95  mov     rdi, [rdi+288h]
0x180025c9c  mov     ebx, [rsp+48h+arg_0]
0x180025ca0  mov     rsi, [rsp+48h+pv]
0x180025ca5  lea     r14, [rdi+270h]
0x180025cac  mov     rcx, [r14]; pv
0x180025caf  call    cs:__imp_CoTaskMemFree
0x180025cb5  mov     [r14], rbp
0x180025cb8  mov     [rdi+278h], ebx
0x180025cbe  test    rsi, rsi
0x180025cc1  jz      short loc_180025CE4
0x180025cc3  or      r9, 0FFFFFFFFFFFFFFFFh
0x180025cc7  inc     r9
0x180025cca  cmp     [rsi+r9*2], bp
0x180025ccf  jnz     short loc_180025CC7
0x180025cd1  mov     r8, rsi
0x180025cd4  mov     [rsp+48h+var_20], r14
0x180025cd9  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180025cde  mov     ebx, eax
0x180025ce0  test    eax, eax
0x180025ce2  js      short loc_180025D00
0x180025ce4  mov     rcx, [rdi+268h]; hEvent
0x180025ceb  call    cs:__imp_SetEvent
0x180025cf1  test    eax, eax
0x180025cf3  jz      short loc_180025CF9
0x180025cf5  mov     ebx, ebp
0x180025cf7  jmp     short loc_180025D00
0x180025cf9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025cfe  mov     ebx, eax
0x180025d00  mov     rcx, [rsp+48h+pv]; pv
0x180025d05  call    cs:__imp_CoTaskMemFree
0x180025d0b  jmp     short loc_180025D24
0x180025d0d  lea     rdx, aIgnoringReques_0; "Ignoring request for HidAcc string-- No"...
0x180025d14  jmp     short loc_180025D1D
0x180025d16  lea     rdx, aIgnoringReques; "Ignoring request for HidAcc string-- Ac"...
0x180025d1d  xor     ecx, ecx
0x180025d1f  call    UnattendLogW
0x180025d24  mov     rbp, [rsp+48h+arg_18]
0x180025d29  mov     eax, ebx
0x180025d2b  mov     rbx, [rsp+48h+arg_8]
0x180025d30  add     rsp, 30h
0x180025d34  pop     r14
0x180025d36  pop     rdi
0x180025d37  pop     rsi
0x180025d38  retn
```
