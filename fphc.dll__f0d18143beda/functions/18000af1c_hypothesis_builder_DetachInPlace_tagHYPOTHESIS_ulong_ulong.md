# _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)

- ea: `0x18000af1c`
- end: `0x18000afc1`
- name: `?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z`
- size: `165`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, struct tagHYPOTHESIS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ad84`

## callees

- `0x18000af1c`
- `0x18000afc8`
- `0x18000edb8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af5d`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::DetachInPlace(
        WCHAR **this,
        struct tagHYPOTHESIS *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  _OWORD *v8; // rcx
  WCHAR *v9; // rax
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  _hypothesis_builder::DoDetach((_hypothesis_builder *)this, (struct tagHYPOTHESIS **)&pv);
  v8 = pv;
  if ( pv )
  {
    *(_OWORD *)&a2->pwszClassName = *(_OWORD *)pv;
    *(_OWORD *)&a2->celt = v8[1];
    CoTaskMemFree(v8);
  }
  else
  {
    if ( *((_DWORD *)this + 4) || this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    a2->pwszClassName = *this;
    v9 = this[1];
    *this = 0;
    a2->pwszDescription = v9;
    this[1] = 0;
    a2->celt = 0;
    a2->rgAttributes = 0;
  }
  *a3 = 1;
  if ( a4 )
    *a4 = 32;
  return 0;
}

```

## disassembly

```asm
0x18000af1c  push    rbx
0x18000af1e  push    rsi
0x18000af1f  push    rdi
0x18000af20  push    r14
0x18000af22  sub     rsp, 28h
0x18000af26  mov     rdi, rdx
0x18000af29  mov     [rsp+48h+pv], 0
0x18000af32  lea     rdx, [rsp+48h+pv]; struct tagHYPOTHESIS **
0x18000af37  mov     rsi, r9
0x18000af3a  mov     r14, r8
0x18000af3d  mov     rbx, rcx
0x18000af40  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x18000af45  mov     rcx, [rsp+48h+pv]; pv
0x18000af4a  test    rcx, rcx
0x18000af4d  jz      short loc_18000AF65
0x18000af4f  movups  xmm0, xmmword ptr [rcx]
0x18000af52  movups  xmmword ptr [rdi], xmm0
0x18000af55  movups  xmm1, xmmword ptr [rcx+10h]
0x18000af59  movups  xmmword ptr [rdi+10h], xmm1
0x18000af5d  call    cs:__imp_CoTaskMemFree
0x18000af63  jmp     short loc_18000AFA3
0x18000af65  cmp     dword ptr [rbx+10h], 0
0x18000af69  jnz     short loc_18000AF72
0x18000af6b  cmp     qword ptr [rbx+18h], 0
0x18000af70  jz      short loc_18000AF77
0x18000af72  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000af77  mov     rax, [rbx]
0x18000af7a  mov     [rdi], rax
0x18000af7d  mov     rax, [rbx+8]
0x18000af81  mov     qword ptr [rbx], 0
0x18000af88  mov     [rdi+8], rax
0x18000af8c  mov     qword ptr [rbx+8], 0
0x18000af94  mov     dword ptr [rdi+10h], 0
0x18000af9b  mov     qword ptr [rdi+18h], 0
0x18000afa3  mov     dword ptr [r14], 1
0x18000afaa  test    rsi, rsi
0x18000afad  jz      short loc_18000AFB5
0x18000afaf  mov     dword ptr [rsi], 20h ; ' '
0x18000afb5  xor     eax, eax
0x18000afb7  add     rsp, 28h
0x18000afbb  pop     r14
0x18000afbd  pop     rdi
0x18000afbe  pop     rsi
0x18000afbf  pop     rbx
0x18000afc0  retn
```
