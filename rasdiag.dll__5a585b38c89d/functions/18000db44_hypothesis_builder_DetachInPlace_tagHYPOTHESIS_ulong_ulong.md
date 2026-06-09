# _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)

- ea: `0x18000db44`
- end: `0x18000dbf0`
- name: `?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z`
- size: `172`
- prototype: `__int64 __fastcall(WCHAR **this, struct tagHYPOTHESIS *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800086b0`

## callees

- `0x18000db44`
- `0x18000dbf8`
- `0x18000dd64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db85`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::DetachInPlace(
        WCHAR **this,
        struct tagHYPOTHESIS *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  _OWORD *v11; // rcx
  WCHAR *v12; // rax
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  _hypothesis_builder::DoDetach((_hypothesis_builder *)this, (struct tagHYPOTHESIS **)&pv);
  v11 = pv;
  if ( pv )
  {
    *(_OWORD *)&a2->pwszClassName = *(_OWORD *)pv;
    *(_OWORD *)&a2->celt = v11[1];
    CoTaskMemFree(v11);
  }
  else
  {
    if ( *((_DWORD *)this + 4) || this[3] )
      MicrosoftTelemetryAssertTriggeredNoArgs(0, v8, v9, v10);
    a2->pwszClassName = *this;
    v12 = this[1];
    *this = 0;
    a2->pwszDescription = v12;
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
0x18000db44  push    rbx
0x18000db46  push    rsi
0x18000db47  push    rdi
0x18000db48  push    r14
0x18000db4a  sub     rsp, 28h
0x18000db4e  mov     rdi, rdx
0x18000db51  mov     [rsp+48h+pv], 0
0x18000db5a  lea     rdx, [rsp+48h+pv]; struct tagHYPOTHESIS **
0x18000db5f  mov     rsi, r9
0x18000db62  mov     r14, r8
0x18000db65  mov     rbx, rcx
0x18000db68  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x18000db6d  mov     rcx, [rsp+48h+pv]; pv
0x18000db72  test    rcx, rcx
0x18000db75  jz      short loc_18000DB93
0x18000db77  movups  xmm0, xmmword ptr [rcx]
0x18000db7a  movups  xmmword ptr [rdi], xmm0
0x18000db7d  movups  xmm1, xmmword ptr [rcx+10h]
0x18000db81  movups  xmmword ptr [rdi+10h], xmm1
0x18000db85  call    cs:__imp_CoTaskMemFree
0x18000db8c  nop     dword ptr [rax+rax+00h]
0x18000db91  jmp     short loc_18000DBD1
0x18000db93  cmp     dword ptr [rbx+10h], 0
0x18000db97  jnz     short loc_18000DBA0
0x18000db99  cmp     qword ptr [rbx+18h], 0
0x18000db9e  jz      short loc_18000DBA5
0x18000dba0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dba5  mov     rax, [rbx]
0x18000dba8  mov     [rdi], rax
0x18000dbab  mov     rax, [rbx+8]
0x18000dbaf  mov     qword ptr [rbx], 0
0x18000dbb6  mov     [rdi+8], rax
0x18000dbba  mov     qword ptr [rbx+8], 0
0x18000dbc2  mov     dword ptr [rdi+10h], 0
0x18000dbc9  mov     qword ptr [rdi+18h], 0
0x18000dbd1  mov     dword ptr [r14], 1
0x18000dbd8  test    rsi, rsi
0x18000dbdb  jz      short loc_18000DBE3
0x18000dbdd  mov     dword ptr [rsi], 20h ; ' '
0x18000dbe3  xor     eax, eax
0x18000dbe5  add     rsp, 28h
0x18000dbe9  pop     r14
0x18000dbeb  pop     rdi
0x18000dbec  pop     rsi
0x18000dbed  pop     rbx
0x18000dbee  retn
```
