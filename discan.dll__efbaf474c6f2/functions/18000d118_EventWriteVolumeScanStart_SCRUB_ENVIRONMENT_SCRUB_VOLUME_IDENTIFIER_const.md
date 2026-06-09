# EventWriteVolumeScanStart(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *)

- ea: `0x18000d118`
- end: `0x18000d2e4`
- name: `?EventWriteVolumeScanStart@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@@Z`
- size: `460`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _SCRUB_VOLUME_IDENTIFIER *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ec84`

## callees

- `0x180001070`
- `0x1800010f4`
- `0x18000166c`
- `0x18000d118`
- `0x180011414`
- `0x180011508`

## pseudocode

```c
void __fastcall EventWriteVolumeScanStart(struct _SCRUB_ENVIRONMENT *a1, const struct _SCRUB_VOLUME_IDENTIFIER *a2)
{
  __int64 *v2; // rdi
  const struct _SCRUB_VOLUME_IDENTIFIER *v3; // r8
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // rsi
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // [rsp+70h] [rbp-10h] BYREF
  __int64 v13; // [rsp+B0h] [rbp+30h] BYREF
  char *v14; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v15; // [rsp+C8h] [rbp+48h] BYREF

  v2 = (__int64 *)((char *)a2 + 24);
  v3 = a2;
  if ( *((_DWORD *)a1 + 2) )
  {
    v8 = (char *)a2 + 16;
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      McTemplateU0hzr0hzr2qiijjjj_EventWriteTransfer(
        *(_DWORD *)a2 + 20,
        *((_QWORD *)a2 + 1),
        **((_WORD **)a2 + 4) >> 1,
        *(_QWORD *)(*((_QWORD *)a2 + 4) + 8LL),
        **((_WORD **)a2 + 7) >> 1,
        *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL),
        **(_DWORD **)v8,
        *(_QWORD *)(*(_QWORD *)v8 + 8LL),
        *(_QWORD *)(*(_QWORD *)v8 + 16LL),
        *v2,
        *(_QWORD *)a2 + 20LL,
        *((_QWORD *)a2 + 1),
        *((_QWORD *)a2 + 1) + 16LL);
    if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, v3) )
    {
      v11 = *(_QWORD *)v8;
      v13 = *(_QWORD *)(*(_QWORD *)v8 + 16LL);
      v14 = *(char **)(v11 + 8);
      v15 = *v2;
      v12 = (__int64)a1 + 52;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v11,
        (__int64)byte_180041203,
        v9,
        v10,
        &v12,
        &v15,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
  else
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
      McTemplateU0hzr0hzr2jqjjj_EventWriteTransfer(
        *(_QWORD *)a2 + 20,
        *(_QWORD *)a2,
        **((_WORD **)a2 + 4) >> 1,
        *(_QWORD *)(*((_QWORD *)a2 + 4) + 8LL),
        **((_WORD **)a2 + 7) >> 1,
        *(_QWORD *)(*((_QWORD *)a2 + 7) + 8LL),
        *v2,
        *(_DWORD *)(*(_QWORD *)a2 + 16LL),
        *(_QWORD *)a2 + 20LL,
        *((_QWORD *)a2 + 1),
        *((_QWORD *)a2 + 1) + 16LL);
    if ( (unsigned int)dword_1800470B8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(a1, a2, v3) )
      {
        v13 = *v2;
        v14 = (char *)a1 + 52;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
          v5,
          (__int64)&word_180041266,
          v6,
          v7,
          &v14,
          &v13);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d118  push    rbp
0x18000d11a  push    rbx
0x18000d11b  push    rsi
0x18000d11c  push    rdi
0x18000d11d  push    r14
0x18000d11f  mov     rbp, rsp
0x18000d122  sub     rsp, 80h
0x18000d129  cmp     dword ptr [rcx+8], 0
0x18000d12d  lea     rdi, [rdx+18h]
0x18000d131  mov     r8, rdx
0x18000d134  mov     r14, rcx
0x18000d137  jnz     loc_18000D1F1
0x18000d13d  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000d144  jz      short loc_18000D1A3
0x18000d146  mov     rbx, [r8+38h]
0x18000d14a  mov     r10, [rdx+8]
0x18000d14e  mov     r9, [r8+20h]
0x18000d152  mov     rdx, [rdx]
0x18000d155  movzx   r11d, word ptr [rbx]
0x18000d159  lea     rax, [r10+10h]
0x18000d15d  shr     r11w, 1
0x18000d161  movzx   r8d, word ptr [r9]
0x18000d165  mov     r9, [r9+8]
0x18000d169  lea     rcx, [rdx+14h]
0x18000d16d  mov     [rsp+80h+var_30], rax
0x18000d172  mov     eax, [rdx+10h]
0x18000d175  mov     [rsp+80h+var_38], r10
0x18000d17a  mov     [rsp+80h+var_40], rcx
0x18000d17f  mov     dword ptr [rsp+80h+var_48], eax
0x18000d183  mov     rax, [rdi]
0x18000d186  mov     [rsp+80h+var_50], rax
0x18000d18b  mov     rax, [rbx+8]
0x18000d18f  mov     [rsp+80h+var_58], rax
0x18000d194  shr     r8w, 1
0x18000d198  mov     word ptr [rsp+80h+var_60], r11w
0x18000d19e  call    McTemplateU0hzr0hzr2jqjjj_EventWriteTransfer
0x18000d1a3  mov     eax, cs:dword_1800470B8
0x18000d1a9  cmp     eax, 5
0x18000d1ac  jbe     loc_18000D2D6
0x18000d1b2  call    _tlgKeywordOn
0x18000d1b7  test    al, al
0x18000d1b9  jz      loc_18000D2D6
0x18000d1bf  mov     rax, [rdi]
0x18000d1c2  lea     rdx, word_180041266
0x18000d1c9  mov     [rbp+arg_0], rax
0x18000d1cd  lea     rax, [r14+34h]
0x18000d1d1  mov     [rbp+arg_10], rax
0x18000d1d5  lea     rax, [rbp+arg_0]
0x18000d1d9  mov     [rsp+80h+var_58], rax
0x18000d1de  lea     rax, [rbp+arg_10]
0x18000d1e2  mov     [rsp+80h+var_60], rax
0x18000d1e7  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x18000d1ec  jmp     loc_18000D2D6
0x18000d1f1  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000d1f8  lea     rsi, [rdx+10h]
0x18000d1fc  jz      short loc_18000D270
0x18000d1fe  mov     rbx, [r8+38h]
0x18000d202  mov     rcx, [r8]
0x18000d205  mov     r11, [rsi]
0x18000d208  add     rcx, 14h
0x18000d20c  mov     r9, [r8+20h]
0x18000d210  mov     rdx, [rdx+8]
0x18000d214  movzx   r10d, word ptr [rbx]
0x18000d218  shr     r10w, 1
0x18000d21c  movzx   r8d, word ptr [r9]
0x18000d220  mov     r9, [r9+8]
0x18000d224  lea     rax, [rdx+10h]
0x18000d228  mov     [rsp+80h+var_20], rax
0x18000d22d  mov     rax, [rdi]
0x18000d230  mov     [rsp+80h+var_28], rdx
0x18000d235  mov     [rsp+80h+var_30], rcx
0x18000d23a  mov     [rsp+80h+var_38], rax
0x18000d23f  mov     rax, [r11+10h]
0x18000d243  mov     [rsp+80h+var_40], rax
0x18000d248  mov     rax, [r11+8]
0x18000d24c  mov     [rsp+80h+var_48], rax
0x18000d251  mov     eax, [r11]
0x18000d254  mov     dword ptr [rsp+80h+var_50], eax
0x18000d258  mov     rax, [rbx+8]
0x18000d25c  mov     [rsp+80h+var_58], rax
0x18000d261  shr     r8w, 1
0x18000d265  mov     word ptr [rsp+80h+var_60], r10w
0x18000d26b  call    McTemplateU0hzr0hzr2qiijjjj_EventWriteTransfer
0x18000d270  mov     eax, cs:dword_1800470B8
0x18000d276  cmp     eax, 5
0x18000d279  jbe     short loc_18000D2D6
0x18000d27b  call    _tlgKeywordOn
0x18000d280  test    al, al
0x18000d282  jz      short loc_18000D2D6
0x18000d284  mov     rcx, [rsi]
0x18000d287  lea     rdx, byte_180041203
0x18000d28e  mov     rax, [rcx+10h]
0x18000d292  mov     [rbp+arg_0], rax
0x18000d296  mov     rax, [rcx+8]
0x18000d29a  mov     [rbp+arg_10], rax
0x18000d29e  mov     rax, [rdi]
0x18000d2a1  mov     [rbp+arg_18], rax
0x18000d2a5  lea     rax, [r14+34h]
0x18000d2a9  mov     [rbp+var_10], rax
0x18000d2ad  lea     rax, [rbp+arg_0]
0x18000d2b1  mov     [rsp+80h+var_48], rax
0x18000d2b6  lea     rax, [rbp+arg_10]
0x18000d2ba  mov     [rsp+80h+var_50], rax
0x18000d2bf  lea     rax, [rbp+arg_18]
0x18000d2c3  mov     [rsp+80h+var_58], rax
0x18000d2c8  lea     rax, [rbp+var_10]
0x18000d2cc  mov     [rsp+80h+var_60], rax
0x18000d2d1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18000d2d6  add     rsp, 80h
0x18000d2dd  pop     r14
0x18000d2df  pop     rdi
0x18000d2e0  pop     rsi
0x18000d2e1  pop     rbx
0x18000d2e2  pop     rbp
0x18000d2e3  retn
```
