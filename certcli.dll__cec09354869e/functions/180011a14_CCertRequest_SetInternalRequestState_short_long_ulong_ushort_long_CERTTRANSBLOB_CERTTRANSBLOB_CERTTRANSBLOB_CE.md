# CCertRequest::_SetInternalRequestState(short,long,ulong,ushort *,long,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)

- ea: `0x180011a14`
- end: `0x180011b99`
- name: `?_SetInternalRequestState@CCertRequest@@AEAAJFJKPEAGJPEAU_CERTTRANSBLOB@@111@Z`
- size: `389`
- prototype: `__int64 __fastcall(CCertRequest *this, __int16, int, unsigned int, unsigned __int16 *, int, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *, struct _CERTTRANSBLOB *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001092c`

## callees

- `0x180011a14`
- `0x180011ba0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011afe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011acc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011ae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011afe`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a51`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a69`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a7d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a51`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a69`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180011a7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CCertRequest::_SetInternalRequestState(
        CCertRequest *this,
        __int16 a2,
        int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        struct _CERTTRANSBLOB *a7,
        struct _CERTTRANSBLOB *a8,
        struct _CERTTRANSBLOB *a9,
        struct _CERTTRANSBLOB *a10)
{
  int v12; // eax
  unsigned int v13; // ebp
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx

  *((_DWORD *)this + 32) = a3;
  *((_WORD *)this + 50) = a2;
  *((_DWORD *)this + 26) = 0;
  v12 = CCertRequest::_SetRequestId(this, a4, a5);
  v13 = v12;
  if ( v12 )
    CSPrintErrorLineFile(0x71F02C4u, v12);
  if ( a6 == -2147023067 )
    CSPrintErrorLineFile(0x72302C4u, -2147023067);
  *((_DWORD *)this + 27) = a6;
  if ( a6 )
  {
    CSPrintErrorLineFile(0x72702C4u, a6);
  }
  else
  {
    if ( a3 >= 0 )
    {
      if ( a3 == 2 )
        *((_DWORD *)this + 27) = -2146877420;
    }
    else
    {
      *((_DWORD *)this + 27) = a3;
      *((_DWORD *)this + 32) = 2;
    }
    v14 = (void *)*((_QWORD *)this + 22);
    if ( v14 )
    {
      CoTaskMemFree(v14);
      *((_QWORD *)this + 22) = 0;
    }
    v15 = (void *)*((_QWORD *)this + 24);
    if ( v15 )
    {
      CoTaskMemFree(v15);
      *((_QWORD *)this + 24) = 0;
    }
    v16 = (void *)*((_QWORD *)this + 20);
    if ( v16 )
    {
      CoTaskMemFree(v16);
      *((_QWORD *)this + 20) = 0;
    }
    v17 = (void *)*((_QWORD *)this + 17);
    if ( v17 )
    {
      CoTaskMemFree(v17);
      *((_QWORD *)this + 17) = 0;
    }
    *((_QWORD *)this + 17) = a10->pb;
    *((_QWORD *)this + 22) = a7->pb;
    *((_DWORD *)this + 46) = a7->cb;
    *((_QWORD *)this + 24) = a8->pb;
    *((_DWORD *)this + 50) = a8->cb;
    *((_QWORD *)this + 20) = a9->pb;
    *((_DWORD *)this + 42) = a9->cb;
    a7->pb = 0;
    a7->cb = 0;
    a8->pb = 0;
    a8->cb = 0;
    a9->pb = 0;
    a9->cb = 0;
    a10->pb = 0;
    a10->cb = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180011a14  push    rbx
0x180011a16  push    rbp
0x180011a17  push    rsi
0x180011a18  push    rdi
0x180011a19  push    r14
0x180011a1b  sub     rsp, 20h
0x180011a1f  mov     esi, r8d
0x180011a22  mov     [rcx+80h], r8d
0x180011a29  mov     r8, [rsp+48h+arg_20]; unsigned __int16 *
0x180011a2e  xor     r14d, r14d
0x180011a31  mov     [rcx+64h], dx
0x180011a35  mov     rbx, rcx
0x180011a38  mov     edx, r9d; unsigned int
0x180011a3b  mov     [rcx+68h], r14d
0x180011a3f  call    ?_SetRequestId@CCertRequest@@AEAAJKPEAG@Z; CCertRequest::_SetRequestId(ulong,ushort *)
0x180011a44  mov     ebp, eax
0x180011a46  test    eax, eax
0x180011a48  jz      short loc_180011A57
0x180011a4a  mov     edx, eax
0x180011a4c  mov     ecx, 71F02C4h
0x180011a51  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180011a57  mov     edi, [rsp+48h+arg_28]
0x180011a5b  mov     edx, 80070725h
0x180011a60  cmp     edi, edx
0x180011a62  jnz     short loc_180011A6F
0x180011a64  mov     ecx, 72302C4h
0x180011a69  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180011a6f  mov     [rbx+6Ch], edi
0x180011a72  test    edi, edi
0x180011a74  jz      short loc_180011A88
0x180011a76  mov     edx, edi
0x180011a78  mov     ecx, 72702C4h
0x180011a7d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180011a83  jmp     loc_180011B8C
0x180011a88  test    esi, esi
0x180011a8a  jns     short loc_180011A9B
0x180011a8c  mov     [rbx+6Ch], esi
0x180011a8f  mov     dword ptr [rbx+80h], 2
0x180011a99  jmp     short loc_180011AA7
0x180011a9b  cmp     esi, 2
0x180011a9e  jnz     short loc_180011AA7
0x180011aa0  mov     dword ptr [rbx+6Ch], 80094014h
0x180011aa7  mov     rcx, [rbx+0B0h]; pv
0x180011aae  test    rcx, rcx
0x180011ab1  jz      short loc_180011AC0
0x180011ab3  call    cs:__imp_CoTaskMemFree
0x180011ab9  mov     [rbx+0B0h], r14
0x180011ac0  mov     rcx, [rbx+0C0h]; pv
0x180011ac7  test    rcx, rcx
0x180011aca  jz      short loc_180011AD9
0x180011acc  call    cs:__imp_CoTaskMemFree
0x180011ad2  mov     [rbx+0C0h], r14
0x180011ad9  mov     rcx, [rbx+0A0h]; pv
0x180011ae0  test    rcx, rcx
0x180011ae3  jz      short loc_180011AF2
0x180011ae5  call    cs:__imp_CoTaskMemFree
0x180011aeb  mov     [rbx+0A0h], r14
0x180011af2  mov     rcx, [rbx+88h]; pv
0x180011af9  test    rcx, rcx
0x180011afc  jz      short loc_180011B0B
0x180011afe  call    cs:__imp_CoTaskMemFree
0x180011b04  mov     [rbx+88h], r14
0x180011b0b  mov     r8, [rsp+48h+arg_30]
0x180011b13  mov     rdx, [rsp+48h+arg_38]
0x180011b1b  mov     rcx, [rsp+48h+arg_40]
0x180011b23  mov     r9, [rsp+48h+arg_48]
0x180011b2b  mov     rax, [r9+8]
0x180011b2f  mov     [rbx+88h], rax
0x180011b36  mov     rax, [r8+8]
0x180011b3a  mov     [rbx+0B0h], rax
0x180011b41  mov     eax, [r8]
0x180011b44  mov     [rbx+0B8h], eax
0x180011b4a  mov     rax, [rdx+8]
0x180011b4e  mov     [rbx+0C0h], rax
0x180011b55  mov     eax, [rdx]
0x180011b57  mov     [rbx+0C8h], eax
0x180011b5d  mov     rax, [rcx+8]
0x180011b61  mov     [rbx+0A0h], rax
0x180011b68  mov     eax, [rcx]
0x180011b6a  mov     [rbx+0A8h], eax
0x180011b70  mov     [r8+8], r14
0x180011b74  mov     [r8], r14d
0x180011b77  mov     [rdx+8], r14
0x180011b7b  mov     [rdx], r14d
0x180011b7e  mov     [rcx+8], r14
0x180011b82  mov     [rcx], r14d
0x180011b85  mov     [r9+8], r14
0x180011b89  mov     [r9], r14d
0x180011b8c  mov     eax, ebp
0x180011b8e  add     rsp, 20h
0x180011b92  pop     r14
0x180011b94  pop     rdi
0x180011b95  pop     rsi
0x180011b96  pop     rbp
0x180011b97  pop     rbx
0x180011b98  retn
```
