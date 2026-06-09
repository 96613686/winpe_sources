# SpImportSecurityContext(_SecBuffer *,void *,unsigned __int64 *)

- ea: `0x1800196a0`
- end: `0x180019725`
- name: `?SpImportSecurityContext@@YAJPEAU_SecBuffer@@PEAXPEA_K@Z`
- size: `133`
- prototype: `__int64 __fastcall(struct _SecBuffer *, void *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ebcc`
- `0x18000ec28`
- `0x180019200`
- `0x1800196a0`

## pseudocode

```c
__int64 __fastcall SpImportSecurityContext(struct _SecBuffer *a1, void *a2, unsigned __int64 *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids);
  v6 = WSTImportSecurityContext(a1, a2, a3);
  v7 = v6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids, v6);
  return v7;
}

```

## disassembly

```asm
0x1800196a0  push    rbx
0x1800196a2  push    rbp
0x1800196a3  push    rsi
0x1800196a4  push    rdi
0x1800196a5  sub     rsp, 28h
0x1800196a9  mov     rbx, r8
0x1800196ac  mov     rdi, rdx
0x1800196af  mov     rsi, rcx
0x1800196b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196b9  lea     rbp, WPP_GLOBAL_Control
0x1800196c0  cmp     rcx, rbp
0x1800196c3  jz      short loc_1800196E0
0x1800196c5  test    byte ptr [rcx+1Ch], 8
0x1800196c9  jz      short loc_1800196E0
0x1800196cb  mov     rcx, [rcx+10h]
0x1800196cf  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x1800196d6  mov     edx, 0Ch
0x1800196db  call    WPP_SF_
0x1800196e0  mov     r8, rbx; unsigned __int64 *
0x1800196e3  mov     rdx, rdi; void *
0x1800196e6  mov     rcx, rsi; struct _SecBuffer *
0x1800196e9  call    ?WSTImportSecurityContext@@YAJPEAU_SecBuffer@@PEAXPEA_K@Z; WSTImportSecurityContext(_SecBuffer *,void *,unsigned __int64 *)
0x1800196ee  mov     ebx, eax
0x1800196f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196f7  cmp     rcx, rbp
0x1800196fa  jz      short loc_18001971A
0x1800196fc  test    byte ptr [rcx+1Ch], 8
0x180019700  jz      short loc_18001971A
0x180019702  mov     rcx, [rcx+10h]
0x180019706  lea     r8, WPP_d498c1d731083119c3c39763ddfac1d6_Traceguids
0x18001970d  mov     edx, 0Dh
0x180019712  mov     r9d, eax
0x180019715  call    WPP_SF_d
0x18001971a  mov     eax, ebx
0x18001971c  add     rsp, 28h
0x180019720  pop     rdi
0x180019721  pop     rsi
0x180019722  pop     rbp
0x180019723  pop     rbx
0x180019724  retn
```
