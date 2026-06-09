# CRtSend::GetCertAndSecurityContext(void)

- ea: `0x18001b088`
- end: `0x18001b289`
- name: `?GetCertAndSecurityContext@CRtSend@@AEAAJXZ`
- size: `513`
- prototype: `__int64 __fastcall(CRtSend *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b5fc`

## callees

- `0x180013c74`
- `0x180016178`
- `0x180016944`
- `0x1800176d4`
- `0x18001b088`
- `0x180021010`
- `0x180023c42`

## import_xrefs

- `ADVAPI32!CopySid` at `0x18001b248`
- `ADVAPI32!CopySid` at `0x18001b248`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRtSend::GetCertAndSecurityContext(CRtSend *this)
{
  __int64 v2; // rcx
  const void **v3; // rdx
  __int64 v4; // rcx
  int v5; // edi
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // eax
  UserSecurityContext *v10; // rax
  UserSecurityContext *v11; // rdi
  int v12; // eax
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rsi
  int v16; // eax
  void *v17; // rax
  UserSecurityContext *v18; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 93);
  v3 = (const void **)*((_QWORD *)this + 34);
  if ( !v2 )
  {
    if ( !v3 )
    {
      v4 = *((_QWORD *)this + 94);
      v5 = *(_DWORD *)(v4 + 68);
      if ( v5 < 0 )
      {
        LogMsgHR(v5, (wchar_t *)L"rt/CRtSend", 0xC8u);
        return (unsigned int)v5;
      }
      v7 = *(_QWORD *)(v4 + 16);
      if ( !v7 )
      {
        LogMsgHR(-1072824273, (wchar_t *)L"rt/CRtSend", 0xCDu);
        return 3222143023LL;
      }
      *((_QWORD *)this + 96) = v7;
      *((_QWORD *)this + 34) = (char *)this + 768;
      *((_DWORD *)this + 70) = *(_DWORD *)(v4 + 48);
      *((_QWORD *)this + 93) = v4;
      return 0;
    }
    goto LABEL_14;
  }
  if ( !v3 )
  {
    v8 = *(_QWORD *)(v2 + 16);
    *((_QWORD *)this + 96) = v8;
    if ( !v8 )
      return 210;
    *((_QWORD *)this + 34) = (char *)this + 768;
    *((_DWORD *)this + 70) = *(_DWORD *)(v2 + 48);
    return 0;
  }
  v9 = *((_DWORD *)this + 70);
  if ( *(_DWORD *)(v2 + 48) != v9 || memcmp_0(*(const void **)(v2 + 16), *v3, v9) )
  {
LABEL_14:
    v10 = (UserSecurityContext *)MmAllocate(0xC8u);
    v18 = v10;
    if ( v10 )
      v11 = UserSecurityContext::UserSecurityContext(v10);
    else
      v11 = 0;
    v18 = v11;
    v12 = UserSecurityContext::HandleExternalCert(v11, **((unsigned __int8 ***)this + 34), *((_DWORD *)this + 70));
    v13 = v12;
    if ( v12 < 0 )
    {
      LogMsgHR(v12, (wchar_t *)L"rt/rtsecctx", 0x1EAu);
      LogMsgHR(v13, (wchar_t *)L"rt/CRtSend", 0xD2u);
      P<UserSecurityContext>::~P<UserSecurityContext>(&v18);
      return v13;
    }
    v14 = *((_QWORD *)this + 93);
    if ( v14 )
    {
      *((_DWORD *)v11 + 9) = *(_DWORD *)(v14 + 36);
      v15 = *((_QWORD *)this + 93);
      if ( !*(_DWORD *)(v15 + 36) )
      {
        v16 = *(_DWORD *)(v15 + 44);
        *((_DWORD *)v11 + 11) = v16;
        if ( v16 )
        {
          v17 = MmAllocate(*(unsigned int *)(v15 + 44));
          *((_QWORD *)v11 + 1) = v17;
          CopySid(*((_DWORD *)v11 + 11), v17, *(PSID *)(v15 + 8));
        }
      }
    }
    else
    {
      *((_DWORD *)v11 + 9) = *(_DWORD *)(*((_QWORD *)this + 94) + 36LL);
    }
    v18 = 0;
    *((_QWORD *)this + 93) = v11;
    P<UserSecurityContext>::~P<UserSecurityContext>(&v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b088  mov     [rsp+arg_8], rbx
0x18001b08d  mov     [rsp+arg_10], rsi
0x18001b092  push    rdi
0x18001b093  sub     rsp, 20h
0x18001b097  mov     rbx, rcx
0x18001b09a  mov     rcx, [rcx+2E8h]
0x18001b0a1  mov     rdx, [rbx+110h]
0x18001b0a8  test    rcx, rcx
0x18001b0ab  jnz     loc_18001B132
0x18001b0b1  test    rdx, rdx
0x18001b0b4  jnz     loc_18001B18B
0x18001b0ba  mov     rcx, [rbx+2F0h]
0x18001b0c1  mov     edi, [rcx+44h]
0x18001b0c4  test    edi, edi
0x18001b0c6  jns     short loc_18001B0E3
0x18001b0c8  mov     r8d, 0C8h; unsigned __int16
0x18001b0ce  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001b0d5  mov     ecx, edi; int
0x18001b0d7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001b0dc  mov     eax, edi
0x18001b0de  jmp     loc_18001B279
0x18001b0e3  mov     rdx, [rcx+10h]
0x18001b0e7  test    rdx, rdx
0x18001b0ea  jnz     short loc_18001B10C
0x18001b0ec  mov     r8d, 0CDh; unsigned __int16
0x18001b0f2  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001b0f9  mov     ebx, 0C00E002Fh
0x18001b0fe  mov     ecx, ebx; int
0x18001b100  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001b105  mov     eax, ebx
0x18001b107  jmp     loc_18001B279
0x18001b10c  lea     rax, [rbx+300h]
0x18001b113  mov     [rax], rdx
0x18001b116  mov     [rbx+110h], rax
0x18001b11d  mov     eax, [rcx+30h]
0x18001b120  mov     [rbx+118h], eax
0x18001b126  mov     [rbx+2E8h], rcx
0x18001b12d  jmp     loc_18001B277
0x18001b132  test    rdx, rdx
0x18001b135  jnz     short loc_18001B169
0x18001b137  mov     rax, [rcx+10h]
0x18001b13b  lea     rdx, [rbx+300h]
0x18001b142  mov     [rdx], rax
0x18001b145  test    rax, rax
0x18001b148  jnz     short loc_18001B154
0x18001b14a  mov     eax, 0D2h
0x18001b14f  jmp     loc_18001B279
0x18001b154  mov     [rbx+110h], rdx
0x18001b15b  mov     eax, [rcx+30h]
0x18001b15e  mov     [rbx+118h], eax
0x18001b164  jmp     loc_18001B277
0x18001b169  mov     eax, [rbx+118h]
0x18001b16f  cmp     [rcx+30h], eax
0x18001b172  jnz     short loc_18001B18B
0x18001b174  mov     r8d, eax; Size
0x18001b177  mov     rdx, [rdx]; Buf2
0x18001b17a  mov     rcx, [rcx+10h]; Buf1
0x18001b17e  call    memcmp_0
0x18001b183  test    eax, eax
0x18001b185  jz      loc_18001B277
0x18001b18b  mov     ecx, 0C8h; unsigned __int64
0x18001b190  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001b195  mov     [rsp+28h+arg_0], rax
0x18001b19a  test    rax, rax
0x18001b19d  jz      short loc_18001B1AC
0x18001b19f  mov     rcx, rax; this
0x18001b1a2  call    ??0UserSecurityContext@@QEAA@XZ; UserSecurityContext::UserSecurityContext(void)
0x18001b1a7  mov     rdi, rax
0x18001b1aa  jmp     short loc_18001B1AE
0x18001b1ac  xor     edi, edi
0x18001b1ae  mov     [rsp+28h+arg_0], rdi
0x18001b1b3  mov     rdx, [rbx+110h]
0x18001b1ba  mov     r8d, [rbx+118h]; unsigned int
0x18001b1c1  mov     rdx, [rdx]; unsigned __int8 *
0x18001b1c4  mov     rcx, rdi; this
0x18001b1c7  call    ?HandleExternalCert@UserSecurityContext@@AEAAJPEAEK@Z; UserSecurityContext::HandleExternalCert(uchar *,ulong)
0x18001b1cc  mov     esi, eax
0x18001b1ce  test    eax, eax
0x18001b1d0  jns     short loc_18001B209
0x18001b1d2  mov     r8d, 1EAh; unsigned __int16
0x18001b1d8  lea     rdx, aRtRtsecctx; "rt/rtsecctx"
0x18001b1df  mov     ecx, eax; int
0x18001b1e1  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001b1e6  mov     r8d, 0D2h; unsigned __int16
0x18001b1ec  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001b1f3  mov     ecx, esi; int
0x18001b1f5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001b1fa  nop
0x18001b1fb  lea     rcx, [rsp+28h+arg_0]
0x18001b200  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x18001b205  mov     eax, esi
0x18001b207  jmp     short loc_18001B279
0x18001b209  mov     rax, [rbx+2E8h]
0x18001b210  test    rax, rax
0x18001b213  jz      short loc_18001B250
0x18001b215  mov     eax, [rax+24h]
0x18001b218  mov     [rdi+24h], eax
0x18001b21b  mov     rsi, [rbx+2E8h]
0x18001b222  cmp     dword ptr [rsi+24h], 0
0x18001b226  jnz     short loc_18001B25D
0x18001b228  mov     eax, [rsi+2Ch]
0x18001b22b  mov     [rdi+2Ch], eax
0x18001b22e  test    eax, eax
0x18001b230  jz      short loc_18001B25D
0x18001b232  mov     ecx, [rsi+2Ch]; unsigned __int64
0x18001b235  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001b23a  mov     [rdi+8], rax
0x18001b23e  mov     r8, [rsi+8]; pSourceSid
0x18001b242  mov     rdx, rax; pDestinationSid
0x18001b245  mov     ecx, [rdi+2Ch]; nDestinationSidLength
0x18001b248  call    cs:__imp_CopySid
0x18001b24e  jmp     short loc_18001B25D
0x18001b250  mov     rax, [rbx+2F0h]
0x18001b257  mov     ecx, [rax+24h]
0x18001b25a  mov     [rdi+24h], ecx
0x18001b25d  mov     [rsp+28h+arg_0], 0
0x18001b266  mov     [rbx+2E8h], rdi
0x18001b26d  lea     rcx, [rsp+28h+arg_0]
0x18001b272  call    ??1?$P@VUserSecurityContext@@@@QEAA@XZ; P<UserSecurityContext>::~P<UserSecurityContext>(void)
0x18001b277  xor     eax, eax
0x18001b279  mov     rbx, [rsp+28h+arg_8]
0x18001b27e  mov     rsi, [rsp+28h+arg_10]
0x18001b283  add     rsp, 20h
0x18001b287  pop     rdi
0x18001b288  retn
```
