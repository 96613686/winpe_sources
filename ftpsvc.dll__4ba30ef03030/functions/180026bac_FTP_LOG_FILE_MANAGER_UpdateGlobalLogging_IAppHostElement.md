# FTP_LOG_FILE_MANAGER::UpdateGlobalLogging(IAppHostElement *)

- ea: `0x180026bac`
- end: `0x180026da3`
- name: `?UpdateGlobalLogging@FTP_LOG_FILE_MANAGER@@QEAAJPEAUIAppHostElement@@@Z`
- size: `503`
- prototype: `int(FTP_LOG_FILE_MANAGER *__hidden this, struct IAppHostElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000d7e0`

## callees

- `0x180001210`
- `0x180001250`
- `0x180026bac`
- `0x180026df8`
- `0x180026fdc`
- `0x180027010`
- `0x180045b0c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180026c8e`
- `msvcrt!_wcsicmp` at `0x180026c8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180026cc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180026d04`
- `OLEAUT32!__imp_SysFreeString` at `0x180026cc4`
- `OLEAUT32!__imp_SysFreeString` at `0x180026d04`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026bbf`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180026bbf`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180026d92`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180026d92`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_LOG_FILE_MANAGER::UpdateGlobalLogging(FTP_LOG_FILE_MANAGER *this, struct IAppHostElement *a2)
{
  char *v4; // rax
  volatile signed __int32 *v5; // rbx
  int v6; // esi
  __int64 v7; // rdx
  int v8; // ecx
  OLECHAR *v9; // rcx
  volatile signed __int32 *v10; // rsi
  OLECHAR *v11; // rcx
  FTP_LOGGING *v12; // rax
  FTP_LOGGING *v13; // rbx
  FTP_LOGGING *v14; // rcx

  CReaderWriterLock3::WriteLock((FTP_LOG_FILE_MANAGER *)((char *)this + 48));
  v4 = (char *)operator new(0x38u);
  v5 = (volatile signed __int32 *)v4;
  if ( !v4 )
    goto LABEL_37;
  *(_QWORD *)(v4 + 4) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *((_QWORD *)v4 + 3) = 0;
  *(_DWORD *)v4 = 1129072454;
  v6 = FTP_GLOBAL_LOGGING_CONFIG_ELEMENT::Initialize((FTP_GLOBAL_LOGGING_CONFIG_ELEMENT *)v4, a2);
  if ( v6 < 0 )
    goto LABEL_19;
  v7 = *((_QWORD *)this + 2);
  if ( v7 )
  {
    *((_DWORD *)this + 8) = 0;
    v8 = 0;
    if ( *((_DWORD *)v5 + 2) != *(_DWORD *)(v7 + 8) )
    {
      v8 = 2;
      *((_DWORD *)this + 8) = 2;
    }
    if ( *((_DWORD *)v5 + 3) != *(_DWORD *)(v7 + 12) )
      *((_DWORD *)this + 8) = v8 | 1;
    if ( *((_DWORD *)v5 + 13) != *(_DWORD *)(v7 + 52)
      || *((_DWORD *)v5 + 9) != *(_DWORD *)(v7 + 36)
      || *((_DWORD *)v5 + 12) != *(_DWORD *)(v7 + 48)
      || *((_DWORD *)v5 + 4) != *(_DWORD *)(v7 + 16)
      || *((_DWORD *)v5 + 8) != *(_DWORD *)(v7 + 32)
      || *((_QWORD *)v5 + 5) != *(_QWORD *)(v7 + 40)
      || _wcsicmp(*((const wchar_t **)v5 + 3), *(const wchar_t **)(v7 + 24)) )
    {
      *((_DWORD *)this + 8) |= 4u;
    }
  }
  else
  {
    *((_DWORD *)this + 8) = 15;
  }
  if ( !*((_DWORD *)this + 8) )
  {
    v6 = 0;
LABEL_19:
    if ( _InterlockedExchangeAdd(v5 + 1, 0xFFFFFFFF) == 1 )
    {
      *v5 = 1668048742;
      v9 = (OLECHAR *)*((_QWORD *)v5 + 3);
      if ( v9 )
      {
        SysFreeString(v9);
        *((_QWORD *)v5 + 3) = 0;
      }
      operator delete((void *)v5);
    }
    goto LABEL_38;
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)this + 2);
  if ( v10 && _InterlockedExchangeAdd(v10 + 1, 0xFFFFFFFF) == 1 )
  {
    *v10 = 1668048742;
    v11 = (OLECHAR *)*((_QWORD *)v10 + 3);
    if ( v11 )
    {
      SysFreeString(v11);
      *((_QWORD *)v10 + 3) = 0;
    }
    operator delete((void *)v10);
  }
  *((_QWORD *)this + 2) = v5;
  v12 = (FTP_LOGGING *)operator new(0x68u);
  v13 = v12 ? FTP_LOGGING::FTP_LOGGING(v12) : 0LL;
  if ( !v13 )
  {
LABEL_37:
    v6 = -2147024882;
    goto LABEL_38;
  }
  v6 = FTP_LOGGING::Initialize(
         v13,
         (const unsigned __int16 **)(*((_QWORD *)this + 2) + 16LL),
         *(_DWORD *)(*((_QWORD *)this + 2) + 12LL),
         0,
         0);
  if ( v6 < 0 )
  {
    FTP_LOGGING::DereferenceFtpLogging(v13);
  }
  else
  {
    v14 = (FTP_LOGGING *)*((_QWORD *)this + 3);
    if ( v14 )
      FTP_LOGGING::DereferenceFtpLogging(v14);
    *((_QWORD *)this + 3) = v13;
  }
LABEL_38:
  CReaderWriterLock3::WriteUnlock((FTP_LOG_FILE_MANAGER *)((char *)this + 48));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026bac  push    rbx
0x180026bae  push    rbp
0x180026baf  push    rsi
0x180026bb0  push    rdi
0x180026bb1  sub     rsp, 38h
0x180026bb5  mov     rsi, rdx
0x180026bb8  mov     rdi, rcx
0x180026bbb  add     rcx, 30h ; '0'
0x180026bbf  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180026bc5  mov     ecx, 38h ; '8'; Size
0x180026bca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026bcf  mov     rbx, rax
0x180026bd2  mov     [rsp+58h+arg_0], rax
0x180026bd7  test    rax, rax
0x180026bda  jz      loc_180026D89
0x180026be0  mov     qword ptr [rax+4], 1
0x180026be8  mov     dword ptr [rax+0Ch], 1
0x180026bef  mov     qword ptr [rax+18h], 0
0x180026bf7  mov     dword ptr [rax], 434C4746h
0x180026bfd  test    rax, rax
0x180026c00  jz      loc_180026D89
0x180026c06  mov     rdx, rsi; struct IAppHostElement *
0x180026c09  mov     rcx, rax; this
0x180026c0c  call    ?Initialize@FTP_GLOBAL_LOGGING_CONFIG_ELEMENT@@QEAAJPEAUIAppHostElement@@@Z; FTP_GLOBAL_LOGGING_CONFIG_ELEMENT::Initialize(IAppHostElement *)
0x180026c11  mov     esi, eax
0x180026c13  test    eax, eax
0x180026c15  js      loc_180026CA4
0x180026c1b  mov     rdx, [rdi+10h]
0x180026c1f  test    rdx, rdx
0x180026c22  jnz     short loc_180026C2D
0x180026c24  mov     dword ptr [rdi+20h], 0Fh
0x180026c2b  jmp     short loc_180026C9C
0x180026c2d  mov     dword ptr [rdi+20h], 0
0x180026c34  xor     ecx, ecx
0x180026c36  mov     eax, [rdx+8]
0x180026c39  cmp     [rbx+8], eax
0x180026c3c  jz      short loc_180026C46
0x180026c3e  mov     ecx, 2
0x180026c43  mov     [rdi+20h], ecx
0x180026c46  mov     eax, [rdx+0Ch]
0x180026c49  cmp     [rbx+0Ch], eax
0x180026c4c  jz      short loc_180026C54
0x180026c4e  or      ecx, 1
0x180026c51  mov     [rdi+20h], ecx
0x180026c54  mov     eax, [rdx+34h]
0x180026c57  cmp     [rbx+34h], eax
0x180026c5a  jnz     short loc_180026C98
0x180026c5c  mov     eax, [rdx+24h]
0x180026c5f  cmp     [rbx+24h], eax
0x180026c62  jnz     short loc_180026C98
0x180026c64  mov     eax, [rdx+30h]
0x180026c67  cmp     [rbx+30h], eax
0x180026c6a  jnz     short loc_180026C98
0x180026c6c  mov     eax, [rdx+10h]
0x180026c6f  cmp     [rbx+10h], eax
0x180026c72  jnz     short loc_180026C98
0x180026c74  mov     eax, [rdx+20h]
0x180026c77  cmp     [rbx+20h], eax
0x180026c7a  jnz     short loc_180026C98
0x180026c7c  mov     rax, [rdx+28h]
0x180026c80  cmp     [rbx+28h], rax
0x180026c84  jnz     short loc_180026C98
0x180026c86  mov     rdx, [rdx+18h]; String2
0x180026c8a  mov     rcx, [rbx+18h]; String1
0x180026c8e  call    cs:__imp__wcsicmp
0x180026c94  test    eax, eax
0x180026c96  jz      short loc_180026C9C
0x180026c98  or      dword ptr [rdi+20h], 4
0x180026c9c  cmp     dword ptr [rdi+20h], 0
0x180026ca0  jnz     short loc_180026CDF
0x180026ca2  xor     esi, esi
0x180026ca4  or      eax, 0FFFFFFFFh
0x180026ca7  lock xadd [rbx+4], eax
0x180026cac  cmp     eax, 1
0x180026caf  jnz     loc_180026D8E
0x180026cb5  mov     dword ptr [rbx], 636C6766h
0x180026cbb  mov     rcx, [rbx+18h]; bstrString
0x180026cbf  test    rcx, rcx
0x180026cc2  jz      short loc_180026CD2
0x180026cc4  call    cs:__imp_SysFreeString
0x180026cca  mov     qword ptr [rbx+18h], 0
0x180026cd2  mov     rcx, rbx; Block
0x180026cd5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026cda  jmp     loc_180026D8E
0x180026cdf  mov     rsi, [rdi+10h]
0x180026ce3  test    rsi, rsi
0x180026ce6  jz      short loc_180026D1A
0x180026ce8  or      eax, 0FFFFFFFFh
0x180026ceb  lock xadd [rsi+4], eax
0x180026cf0  cmp     eax, 1
0x180026cf3  jnz     short loc_180026D1A
0x180026cf5  mov     dword ptr [rsi], 636C6766h
0x180026cfb  mov     rcx, [rsi+18h]; bstrString
0x180026cff  test    rcx, rcx
0x180026d02  jz      short loc_180026D12
0x180026d04  call    cs:__imp_SysFreeString
0x180026d0a  mov     qword ptr [rsi+18h], 0
0x180026d12  mov     rcx, rsi; Block
0x180026d15  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026d1a  mov     [rdi+10h], rbx
0x180026d1e  mov     ecx, 68h ; 'h'; Size
0x180026d23  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026d28  mov     [rsp+58h+arg_0], rax
0x180026d2d  test    rax, rax
0x180026d30  jz      short loc_180026D3F
0x180026d32  mov     rcx, rax; this
0x180026d35  call    ??0FTP_LOGGING@@QEAA@XZ; FTP_LOGGING::FTP_LOGGING(void)
0x180026d3a  mov     rbx, rax
0x180026d3d  jmp     short loc_180026D41
0x180026d3f  xor     ebx, ebx
0x180026d41  test    rbx, rbx
0x180026d44  jz      short loc_180026D89
0x180026d46  mov     r8, [rdi+10h]
0x180026d4a  lea     rdx, [r8+10h]; struct FTP_LOG_FILE_CONFIG_ELEMENT *
0x180026d4e  mov     [rsp+58h+var_38], 0; unsigned int
0x180026d56  xor     r9d, r9d; int
0x180026d59  mov     r8d, [r8+0Ch]; int
0x180026d5d  mov     rcx, rbx; this
0x180026d60  call    ?Initialize@FTP_LOGGING@@QEAAJPEAVFTP_LOG_FILE_CONFIG_ELEMENT@@HHK@Z; FTP_LOGGING::Initialize(FTP_LOG_FILE_CONFIG_ELEMENT *,int,int,ulong)
0x180026d65  mov     esi, eax
0x180026d67  test    eax, eax
0x180026d69  js      short loc_180026D7F
0x180026d6b  mov     rcx, [rdi+18h]; this
0x180026d6f  test    rcx, rcx
0x180026d72  jz      short loc_180026D79
0x180026d74  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180026d79  mov     [rdi+18h], rbx
0x180026d7d  jmp     short loc_180026D8E
0x180026d7f  mov     rcx, rbx; this
0x180026d82  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180026d87  jmp     short loc_180026D8E
0x180026d89  mov     esi, 8007000Eh
0x180026d8e  lea     rcx, [rdi+30h]
0x180026d92  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180026d98  mov     eax, esi
0x180026d9a  add     rsp, 38h
0x180026d9e  pop     rdi
0x180026d9f  pop     rsi
0x180026da0  pop     rbp
0x180026da1  pop     rbx
0x180026da2  retn
```
