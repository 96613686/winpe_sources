# GetECB

- ea: `0x1800044bc`
- end: `0x1800045fe`
- name: `GetECB`
- size: `322`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800066c0`
- `0x180007330`
- `0x180007fd0`

## callees

- `0x1800023f0`
- `0x1800044bc`
- `0x180008ce0`
- `0x180011b62`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800045c0`
- `KERNEL32!LeaveCriticalSection` at `0x1800045c0`
- `KERNEL32!EnterCriticalSection` at `0x180004583`
- `KERNEL32!EnterCriticalSection` at `0x180004583`
- `KERNEL32!SetLastError` at `0x180004534`
- `KERNEL32!SetLastError` at `0x180004534`
- `KERNEL32!GlobalAlloc` at `0x1800044fc`
- `KERNEL32!GlobalAlloc` at `0x1800044fc`

## pseudocode

```c
_QWORD *GetECB()
{
  _QWORD *v0; // rax
  _QWORD *v1; // rbx
  char *v3; // rdx
  char *v4; // rcx
  __int64 v5; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x12u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  v0 = GlobalAlloc(0x40u, 0x88u);
  v1 = v0;
  if ( v0 )
  {
    memset_0(v0, 0, 0x88u);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)pGlobalNPCB + 72));
    v3 = (char *)pGlobalNPCB;
    v4 = (char *)pGlobalNPCB + 160;
    v5 = *((_QWORD *)pGlobalNPCB + 20);
    if ( v5 )
    {
      v1[15] = v5;
      *(_QWORD *)(*(_QWORD *)v4 + 128LL) = v1;
    }
    else
    {
      *((_QWORD *)pGlobalNPCB + 19) = v1;
    }
    *(_QWORD *)v4 = v1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 72));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v1);
    return v1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x13u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    SetLastError(8u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x14u, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x1800044bc  mov     [rsp+arg_0], rbx
0x1800044c1  push    rdi
0x1800044c2  sub     rsp, 20h
0x1800044c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044cd  lea     rdi, WPP_GLOBAL_Control
0x1800044d4  cmp     rcx, rdi
0x1800044d7  jz      short loc_1800044F4
0x1800044d9  test    byte ptr [rcx+1Ch], 1
0x1800044dd  jz      short loc_1800044F4
0x1800044df  mov     rcx, [rcx+10h]
0x1800044e3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800044ea  mov     edx, 12h
0x1800044ef  call    WPP_SF_
0x1800044f4  mov     edx, 88h; dwBytes
0x1800044f9  lea     ecx, [rdx-48h]; uFlags
0x1800044fc  call    cs:__imp_GlobalAlloc
0x180004502  mov     rbx, rax
0x180004505  test    rax, rax
0x180004508  jnz     short loc_180004568
0x18000450a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004511  cmp     rcx, rdi
0x180004514  jz      short loc_18000452F
0x180004516  test    byte ptr [rcx+1Ch], 2
0x18000451a  jz      short loc_18000452F
0x18000451c  mov     rcx, [rcx+10h]
0x180004520  lea     edx, [rax+13h]
0x180004523  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000452a  call    WPP_SF_
0x18000452f  mov     ecx, 8; dwErrCode
0x180004534  call    cs:__imp_SetLastError
0x18000453a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004541  cmp     rcx, rdi
0x180004544  jz      short loc_180004561
0x180004546  test    byte ptr [rcx+1Ch], 2
0x18000454a  jz      short loc_180004561
0x18000454c  mov     rcx, [rcx+10h]
0x180004550  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004557  mov     edx, 14h
0x18000455c  call    WPP_SF_
0x180004561  xor     eax, eax
0x180004563  jmp     loc_1800045F3
0x180004568  xor     edx, edx; Val
0x18000456a  mov     r8d, 88h; Size
0x180004570  mov     rcx, rbx; void *
0x180004573  call    memset_0
0x180004578  mov     rcx, cs:pGlobalNPCB
0x18000457f  add     rcx, 48h ; 'H'; lpCriticalSection
0x180004583  call    cs:__imp_EnterCriticalSection
0x180004589  mov     rdx, cs:pGlobalNPCB
0x180004590  lea     rcx, [rdx+0A0h]
0x180004597  mov     rax, [rcx]
0x18000459a  test    rax, rax
0x18000459d  jz      short loc_1800045AF
0x18000459f  mov     [rbx+78h], rax
0x1800045a3  mov     rax, [rcx]
0x1800045a6  mov     [rax+80h], rbx
0x1800045ad  jmp     short loc_1800045B6
0x1800045af  mov     [rdx+98h], rbx
0x1800045b6  mov     [rcx], rbx
0x1800045b9  mov     rax, rbx
0x1800045bc  lea     rcx, [rdx+48h]; lpCriticalSection
0x1800045c0  call    cs:__imp_LeaveCriticalSection
0x1800045c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045cd  cmp     rcx, rdi
0x1800045d0  jz      short loc_1800045F0
0x1800045d2  test    byte ptr [rcx+1Ch], 1
0x1800045d6  jz      short loc_1800045F0
0x1800045d8  mov     rcx, [rcx+10h]
0x1800045dc  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800045e3  mov     edx, 15h
0x1800045e8  mov     r9, rbx
0x1800045eb  call    WPP_SF_q
0x1800045f0  mov     rax, rbx
0x1800045f3  mov     rbx, [rsp+28h+arg_0]
0x1800045f8  add     rsp, 20h
0x1800045fc  pop     rdi
0x1800045fd  retn
```
