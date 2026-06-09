# CRdpHintApiSink::ClearGeometryOnVC(unsigned __int64)

- ea: `0x140037aec`
- end: `0x140037d0a`
- name: `?ClearGeometryOnVC@CRdpHintApiSink@@IEAAJ_K@Z`
- size: `542`
- prototype: `__int64 __fastcall(CRdpHintApiSink *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x140037d10`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x140011054`
- `0x14001ff80`
- `0x140037aec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037bdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140037ce5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140037ce5`
- `WTSAPI32!WTSVirtualChannelWrite` at `0x140037c6f`
- `WTSAPI32!WTSVirtualChannelWrite` at `0x140037c6f`

## string_xrefs

- `0x140037caf`: `Failed to write on TSGEOMETRY_CHANNEL_NAME DVC`

## pseudocode

```c
__int64 __fastcall CRdpHintApiSink::ClearGeometryOnVC(HANDLE *this, __int64 a2)
{
  PVOID *v4; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v6; // ebx
  unsigned int v7; // eax
  _DWORD *v8; // rax
  _DWORD *v9; // rdi
  unsigned int v10; // eax
  signed int LastError; // eax
  unsigned int v12; // eax
  ULONG pBytesWritten; // [rsp+50h] [rbp+8h] BYREF
  char *v15; // [rsp+60h] [rbp+18h] BYREF

  pBytesWritten = 0;
  v15 = (char *)(this + 7);
  CTSCriticalSection::Lock((CTSCriticalSection *)(this + 7));
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
      CurrentThreadActivityIdPrefix,
      a2);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( this[148] )
  {
    v8 = CoTaskMemAlloc(0x49u);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, 0x49u);
      *v9 = 73;
      v9[1] = 1;
      *((_QWORD *)v9 + 1) = a2;
      v9[4] = 2;
      if ( WTSVirtualChannelWrite(this[148], (PCHAR)v9, 0x49u, &pBytesWritten) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
            v12,
            (__int64)"Failed to write on TSGEOMETRY_CHANNEL_NAME DVC",
            v6);
        }
      }
      CoTaskMemFree(v9);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
          v10,
          (__int64)"\"MAPPED_WINDOW_GEOMETRY_PACKET*\"");
      }
      v6 = -2147024882;
    }
  }
  else
  {
    v6 = -2147467259;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids,
        v7,
        (__int64)"ClearGeometryOnVC: Geometry VC handle is NULL",
        -2147467259);
    }
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140037aec  mov     rax, rsp
0x140037aef  mov     [rax+10h], rbx
0x140037af3  mov     [rax+20h], rbp
0x140037af7  push    rsi
0x140037af8  push    rdi
0x140037af9  push    r14
0x140037afb  sub     rsp, 30h
0x140037aff  mov     rbx, rcx
0x140037b02  mov     dword ptr [rax+8], 0
0x140037b09  add     rcx, 38h ; '8'; this
0x140037b0d  mov     rsi, rdx
0x140037b10  mov     [rax+18h], rcx
0x140037b14  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140037b19  mov     rax, cs:WPP_GLOBAL_Control
0x140037b20  lea     rbp, WPP_GLOBAL_Control
0x140037b27  cmp     rax, rbp
0x140037b2a  jz      short loc_140037B6B
0x140037b2c  test    dword ptr [rax+1Ch], 200h
0x140037b33  jz      short loc_140037B6B
0x140037b35  cmp     byte ptr [rax+19h], 5
0x140037b39  jb      short loc_140037B6B
0x140037b3b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140037b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b47  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140037b4e  mov     edx, 30h ; '0'
0x140037b53  mov     [rsp+48h+var_28], rsi
0x140037b58  mov     r9d, eax
0x140037b5b  mov     rcx, [rcx+10h]
0x140037b5f  call    WPP_SF_Dq
0x140037b64  mov     rax, cs:WPP_GLOBAL_Control
0x140037b6b  cmp     qword ptr [rbx+4A0h], 0
0x140037b73  jnz     short loc_140037BD4
0x140037b75  mov     ebx, 80004005h
0x140037b7a  cmp     rax, rbp
0x140037b7d  jz      loc_140037CEB
0x140037b83  test    byte ptr [rax+1Ch], 8
0x140037b87  jz      loc_140037CEB
0x140037b8d  cmp     byte ptr [rax+19h], 2
0x140037b91  jb      loc_140037CEB
0x140037b97  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140037b9c  lea     rcx, aCleargeometryo; "ClearGeometryOnVC: Geometry VC handle i"...
0x140037ba3  mov     [rsp+48h+var_20], 80004005h
0x140037bab  mov     [rsp+48h+var_28], rcx
0x140037bb0  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140037bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140037bbe  mov     edx, 31h ; '1'
0x140037bc3  mov     r9d, eax
0x140037bc6  mov     rcx, [rcx+10h]
0x140037bca  call    WPP_SF_DsD
0x140037bcf  jmp     loc_140037CEB
0x140037bd4  mov     r14d, 49h ; 'I'
0x140037bda  mov     ecx, r14d; cb
0x140037bdd  call    cs:__imp_CoTaskMemAlloc
0x140037be3  mov     rdi, rax
0x140037be6  test    rax, rax
0x140037be9  jnz     short loc_140037C3B
0x140037beb  mov     rax, cs:WPP_GLOBAL_Control
0x140037bf2  cmp     rax, rbp
0x140037bf5  jz      short loc_140037C31
0x140037bf7  test    byte ptr [rax+1Ch], 8
0x140037bfb  jz      short loc_140037C31
0x140037bfd  cmp     byte ptr [rax+19h], 2
0x140037c01  jb      short loc_140037C31
0x140037c03  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140037c08  lea     rcx, aMappedWindowGe; "\"MAPPED_WINDOW_GEOMETRY_PACKET*\""
0x140037c0f  mov     r9d, eax
0x140037c12  mov     [rsp+48h+var_28], rcx
0x140037c17  lea     edx, [rdi+32h]
0x140037c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140037c21  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140037c28  mov     rcx, [rcx+10h]
0x140037c2c  call    WPP_SF_Ds
0x140037c31  mov     ebx, 8007000Eh
0x140037c36  jmp     loc_140037CEB
0x140037c3b  mov     r8, r14; Size
0x140037c3e  xor     edx, edx; Val
0x140037c40  mov     rcx, rdi; void *
0x140037c43  call    memset_0
0x140037c48  mov     [rdi], r14d
0x140037c4b  lea     r9, [rsp+48h+pBytesWritten]; pBytesWritten
0x140037c50  mov     dword ptr [rdi+4], 1
0x140037c57  mov     r8d, r14d; Length
0x140037c5a  mov     [rdi+8], rsi
0x140037c5e  mov     rdx, rdi; Buffer
0x140037c61  mov     dword ptr [rdi+10h], 2
0x140037c68  mov     rcx, [rbx+4A0h]; hChannelHandle
0x140037c6f  call    cs:__imp_WTSVirtualChannelWrite
0x140037c75  test    eax, eax
0x140037c77  jnz     short loc_140037CE0
0x140037c79  call    cs:__imp_GetLastError
0x140037c7f  mov     ebx, eax
0x140037c81  test    eax, eax
0x140037c83  jle     short loc_140037C8E
0x140037c85  movzx   ebx, ax
0x140037c88  or      ebx, 80070000h
0x140037c8e  test    ebx, ebx
0x140037c90  jns     short loc_140037CE2
0x140037c92  mov     rax, cs:WPP_GLOBAL_Control
0x140037c99  cmp     rax, rbp
0x140037c9c  jz      short loc_140037CE2
0x140037c9e  test    byte ptr [rax+1Ch], 8
0x140037ca2  jz      short loc_140037CE2
0x140037ca4  cmp     byte ptr [rax+19h], 2
0x140037ca8  jb      short loc_140037CE2
0x140037caa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140037caf  lea     rcx, aFailedToWriteO; "Failed to write on TSGEOMETRY_CHANNEL_N"...
0x140037cb6  mov     [rsp+48h+var_20], ebx
0x140037cba  mov     [rsp+48h+var_28], rcx
0x140037cbf  lea     r8, WPP_831ea65fad7736bfdd6b23908d4018f5_Traceguids
0x140037cc6  mov     rcx, cs:WPP_GLOBAL_Control
0x140037ccd  mov     edx, 33h ; '3'
0x140037cd2  mov     r9d, eax
0x140037cd5  mov     rcx, [rcx+10h]
0x140037cd9  call    WPP_SF_DsD
0x140037cde  jmp     short loc_140037CE2
0x140037ce0  xor     ebx, ebx
0x140037ce2  mov     rcx, rdi; pv
0x140037ce5  call    cs:__imp_CoTaskMemFree
0x140037ceb  lea     rcx, [rsp+48h+arg_10]; this
0x140037cf0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140037cf5  mov     rbp, [rsp+48h+arg_18]
0x140037cfa  mov     eax, ebx
0x140037cfc  mov     rbx, [rsp+48h+arg_8]
0x140037d01  add     rsp, 30h
0x140037d05  pop     r14
0x140037d07  pop     rdi
0x140037d08  pop     rsi
0x140037d09  retn
```
