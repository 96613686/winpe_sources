# SpExportSecurityContext(unsigned __int64,ulong,_SecBuffer *,void * *)

- ea: `0x180019560`
- end: `0x1800195ed`
- name: `?SpExportSecurityContext@@YAJ_KKPEAU_SecBuffer@@PEAPEAX@Z`
- size: `141`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned int, struct _SecBuffer *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ebcc`
- `0x18000ec28`
- `0x180018f28`
- `0x180019560`

## pseudocode

```c
__int64 __fastcall SpExportSecurityContext(unsigned __int64 a1, unsigned int a2, struct _SecBuffer *a3, void **a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids);
  v8 = WSTExportSecurityContext(a1, a2, a3, a4);
  v9 = v8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids, v8);
  return v9;
}

```

## disassembly

```asm
0x180019560  push    rbx
0x180019562  push    rbp
0x180019563  push    rsi
0x180019564  push    rdi
0x180019565  push    r14
0x180019567  sub     rsp, 20h
0x18001956b  mov     rbx, r9
0x18001956e  mov     rdi, r8
0x180019571  mov     esi, edx
0x180019573  mov     rbp, rcx
0x180019576  mov     rcx, cs:WPP_GLOBAL_Control
0x18001957d  lea     r14, WPP_GLOBAL_Control
0x180019584  cmp     rcx, r14
0x180019587  jz      short loc_1800195A4
0x180019589  test    byte ptr [rcx+1Ch], 8
0x18001958d  jz      short loc_1800195A4
0x18001958f  mov     rcx, [rcx+10h]
0x180019593  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x18001959a  mov     edx, 0Ah
0x18001959f  call    WPP_SF_
0x1800195a4  mov     r9, rbx; void **
0x1800195a7  mov     r8, rdi; struct _SecBuffer *
0x1800195aa  mov     edx, esi; unsigned int
0x1800195ac  mov     rcx, rbp; unsigned __int64
0x1800195af  call    ?WSTExportSecurityContext@@YAJ_KKPEAU_SecBuffer@@PEAPEAX@Z; WSTExportSecurityContext(unsigned __int64,ulong,_SecBuffer *,void * *)
0x1800195b4  mov     ebx, eax
0x1800195b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195bd  cmp     rcx, r14
0x1800195c0  jz      short loc_1800195E0
0x1800195c2  test    byte ptr [rcx+1Ch], 8
0x1800195c6  jz      short loc_1800195E0
0x1800195c8  mov     rcx, [rcx+10h]
0x1800195cc  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x1800195d3  mov     edx, 0Bh
0x1800195d8  mov     r9d, eax
0x1800195db  call    WPP_SF_d
0x1800195e0  mov     eax, ebx
0x1800195e2  add     rsp, 20h
0x1800195e6  pop     r14
0x1800195e8  pop     rdi
0x1800195e9  pop     rsi
0x1800195ea  pop     rbp
0x1800195eb  pop     rbx
0x1800195ec  retn
```
