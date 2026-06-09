# CMsmqVssWriter::RestoreRegistry(wchar_t const *,void *)

- ea: `0x1800929fc`
- end: `0x180092caf`
- name: `?RestoreRegistry@CMsmqVssWriter@@AEAAJPEB_WPEAX@Z`
- size: `691`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, const wchar_t *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180093cdc`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008da88`
- `0x1800906fc`
- `0x1800929fc`
- `0x180092cb8`
- `0x180093e3c`
- `0x180094090`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180092ab9`
- `msvcrt!free` at `0x180092b04`
- `msvcrt!free` at `0x180092b4b`
- `msvcrt!free` at `0x180092b82`
- `msvcrt!free` at `0x180092bb7`
- `msvcrt!free` at `0x180092bec`
- `msvcrt!free` at `0x180092c33`
- `msvcrt!free` at `0x180092c75`
- `msvcrt!free` at `0x180092c83`
- `msvcrt!free` at `0x180092ab9`
- `msvcrt!free` at `0x180092b04`
- `msvcrt!free` at `0x180092b4b`
- `msvcrt!free` at `0x180092b82`
- `msvcrt!free` at `0x180092bb7`
- `msvcrt!free` at `0x180092bec`
- `msvcrt!free` at `0x180092c33`
- `msvcrt!free` at `0x180092c75`
- `msvcrt!free` at `0x180092c83`

## string_xrefs

- `0x180092a63`: `writer/mqwriter`
- `0x180092aa5`: `writer/mqwriter`
- `0x180092af2`: `writer/mqwriter`
- `0x180092b39`: `writer/mqwriter`
- `0x180092b70`: `writer/mqwriter`
- `0x180092ba5`: `writer/mqwriter`
- `0x180092bda`: `writer/mqwriter`
- `0x180092c21`: `writer/mqwriter`
- `0x180092c63`: `writer/mqwriter`
- `0x180092a2f`: `config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::RestoreRegistry(CMsmqVssWriter *this, const wchar_t *a2, void *a3)
{
  int v5; // eax
  unsigned int v6; // r8d
  unsigned int v7; // ebx
  int TriggersInfo; // eax
  CMsmqVssWriter *v10; // rcx
  const wchar_t *v11; // r8
  void *v12; // rbx
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int updated; // eax
  const wchar_t *v19; // r8
  int v20; // eax
  int v21; // eax
  unsigned int v22; // edi
  void *Block; // [rsp+30h] [rbp-448h] BYREF
  wchar_t v24[256]; // [rsp+40h] [rbp-438h] BYREF
  wchar_t v25[264]; // [rsp+240h] [rbp-238h] BYREF

  v5 = StringCchPrintfW(v25, 0x104u, L"%s\\%s\\%s", a2, L"config", L"msmqreg.bkp");
  v7 = v5;
  if ( v5 < 0 )
  {
    LogMsgHR(v5, (wchar_t *)L"writer/mqwriter", 0xADCu);
    return v7;
  }
  Block = 0;
  TriggersInfo = CMsmqVssWriter::GetTriggersInfo(this, v24, v6, (wchar_t **)&Block);
  v7 = TriggersInfo;
  if ( TriggersInfo < 0 && (_WORD)TriggersInfo != 2 )
  {
    LogMsgHR(TriggersInfo, (wchar_t *)L"writer/mqwriter", 0xAF0u);
    free(Block);
    return v7;
  }
  v11 = (const wchar_t *)*((_QWORD *)this + 5);
  v12 = Block;
  if ( v11 )
  {
    v13 = CMsmqVssWriter::AddRemoveRegCheckpoint((const wchar_t **)this, *((wchar_t **)this + 4), v11, 0x14000A6u);
    v14 = v13;
    if ( v13 < 0 )
    {
      LogMsgHR(v13, (wchar_t *)L"writer/mqwriter", 0xBB8u);
      free(v12);
      return v14;
    }
    if ( v12 )
    {
      v15 = CMsmqVssWriter::AddRemoveRegCheckpoint((const wchar_t **)this, v24, (const wchar_t *)v12, 0x14000A6u);
      v14 = v15;
      if ( v15 < 0 )
      {
        LogMsgHR(v15, (wchar_t *)L"writer/mqwriter", 0xBCCu);
        free(v12);
        return v14;
      }
    }
  }
  v16 = CMsmqVssWriter::RestoreRegistryFromFile(v10, v25, a3);
  v14 = v16;
  if ( v16 < 0 )
  {
    LogMsgHR(v16, (wchar_t *)L"writer/mqwriter", 0xBE0u);
    free(v12);
    return v14;
  }
  v17 = CMsmqVssWriter::SaveComponents(this, *((_DWORD *)this + 13), a3);
  v14 = v17;
  if ( v17 < 0 )
  {
    LogMsgHR(v17, (wchar_t *)L"writer/mqwriter", 0xBF4u);
    free(v12);
    return v14;
  }
  updated = CMsmqVssWriter::UpdateRestoreSeqID(this, a3);
  v14 = updated;
  if ( updated < 0 )
  {
    LogMsgHR(updated, (wchar_t *)L"writer/mqwriter", 0xC08u);
    free(v12);
    return v14;
  }
  v19 = (const wchar_t *)*((_QWORD *)this + 5);
  if ( !v19 )
    goto LABEL_26;
  v20 = CMsmqVssWriter::AddRemoveRegCheckpoint((const wchar_t **)this, *((wchar_t **)this + 4), v19, 0x14000A2u);
  v14 = v20;
  if ( v20 < 0 )
  {
    LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0xC1Cu);
    free(v12);
    return v14;
  }
  if ( v12
    && (v21 = CMsmqVssWriter::AddRemoveRegCheckpoint((const wchar_t **)this, v24, (const wchar_t *)v12, 0x14000A2u),
        v22 = v21,
        v21 < 0) )
  {
    LogMsgHR(v21, (wchar_t *)L"writer/mqwriter", 0xC30u);
    free(v12);
    return v22;
  }
  else
  {
LABEL_26:
    free(v12);
    return 0;
  }
}

```

## disassembly

```asm
0x1800929fc  mov     [rsp+arg_18], rbx
0x180092a01  push    rbp
0x180092a02  push    rsi
0x180092a03  push    rdi
0x180092a04  sub     rsp, 460h
0x180092a0b  mov     rax, cs:__security_cookie
0x180092a12  xor     rax, rsp
0x180092a15  mov     [rsp+478h+var_28], rax
0x180092a1d  mov     rbp, r8
0x180092a20  mov     rdi, rcx
0x180092a23  lea     rax, aMsmqregBkp; "msmqreg.bkp"
0x180092a2a  mov     [rsp+478h+var_450], rax
0x180092a2f  lea     rax, aConfig; "config"
0x180092a36  mov     [rsp+478h+var_458], rax
0x180092a3b  mov     r9, rdx
0x180092a3e  lea     r8, aSSS; "%s\\%s\\%s"
0x180092a45  mov     edx, 104h; unsigned __int64
0x180092a4a  lea     rcx, [rsp+478h+var_238]; wchar_t *
0x180092a52  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180092a57  mov     ebx, eax
0x180092a59  test    eax, eax
0x180092a5b  jns     short loc_180092A78
0x180092a5d  mov     r8d, 0ADCh; unsigned __int16
0x180092a63  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092a6a  mov     ecx, eax; int
0x180092a6c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092a71  mov     eax, ebx
0x180092a73  jmp     loc_180092C8C
0x180092a78  mov     [rsp+478h+Block], 0
0x180092a81  lea     r9, [rsp+478h+Block]; wchar_t **
0x180092a86  lea     rdx, [rsp+478h+var_438]; wchar_t *
0x180092a8b  mov     rcx, rdi; this
0x180092a8e  call    ?GetTriggersInfo@CMsmqVssWriter@@AEAAJPEA_WKPEAPEA_W@Z; CMsmqVssWriter::GetTriggersInfo(wchar_t *,ulong,wchar_t * *)
0x180092a93  mov     ebx, eax
0x180092a95  test    eax, eax
0x180092a97  jns     short loc_180092AC2
0x180092a99  cmp     bx, 2
0x180092a9d  jz      short loc_180092AC2
0x180092a9f  mov     r8d, 0AF0h; unsigned __int16
0x180092aa5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092aac  mov     ecx, eax; int
0x180092aae  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092ab3  nop
0x180092ab4  mov     rcx, [rsp+478h+Block]; Block
0x180092ab9  call    cs:__imp_free
0x180092abf  nop
0x180092ac0  jmp     short loc_180092A71
0x180092ac2  mov     r8, [rdi+28h]; wchar_t *
0x180092ac6  mov     rbx, [rsp+478h+Block]
0x180092acb  test    r8, r8
0x180092ace  jz      loc_180092B54
0x180092ad4  mov     r9d, 14000A6h; unsigned int
0x180092ada  mov     rdx, [rdi+20h]; wchar_t *
0x180092ade  mov     rcx, rdi; this
0x180092ae1  call    ?AddRemoveRegCheckpoint@CMsmqVssWriter@@AEAAJPEB_W0K@Z; CMsmqVssWriter::AddRemoveRegCheckpoint(wchar_t const *,wchar_t const *,ulong)
0x180092ae6  mov     esi, eax
0x180092ae8  test    eax, eax
0x180092aea  jns     short loc_180092B12
0x180092aec  mov     r8d, 0BB8h; unsigned __int16
0x180092af2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092af9  mov     ecx, eax; int
0x180092afb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092b00  nop
0x180092b01  mov     rcx, rbx; Block
0x180092b04  call    cs:__imp_free
0x180092b0a  nop
0x180092b0b  mov     eax, esi
0x180092b0d  jmp     loc_180092C8C
0x180092b12  test    rbx, rbx
0x180092b15  jz      short loc_180092B54
0x180092b17  mov     r9d, 14000A6h; unsigned int
0x180092b1d  mov     r8, rbx; wchar_t *
0x180092b20  lea     rdx, [rsp+478h+var_438]; wchar_t *
0x180092b25  mov     rcx, rdi; this
0x180092b28  call    ?AddRemoveRegCheckpoint@CMsmqVssWriter@@AEAAJPEB_W0K@Z; CMsmqVssWriter::AddRemoveRegCheckpoint(wchar_t const *,wchar_t const *,ulong)
0x180092b2d  mov     esi, eax
0x180092b2f  test    eax, eax
0x180092b31  jns     short loc_180092B54
0x180092b33  mov     r8d, 0BCCh; unsigned __int16
0x180092b39  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092b40  mov     ecx, eax; int
0x180092b42  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092b47  nop
0x180092b48  mov     rcx, rbx; Block
0x180092b4b  call    cs:__imp_free
0x180092b51  nop
0x180092b52  jmp     short loc_180092B0B
0x180092b54  mov     r8, rbp; void *
0x180092b57  lea     rdx, [rsp+478h+var_238]; wchar_t *
0x180092b5f  call    ?RestoreRegistryFromFile@CMsmqVssWriter@@AEAAJPEB_WPEAX@Z; CMsmqVssWriter::RestoreRegistryFromFile(wchar_t const *,void *)
0x180092b64  mov     esi, eax
0x180092b66  test    eax, eax
0x180092b68  jns     short loc_180092B8B
0x180092b6a  mov     r8d, 0BE0h; unsigned __int16
0x180092b70  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092b77  mov     ecx, eax; int
0x180092b79  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092b7e  nop
0x180092b7f  mov     rcx, rbx; Block
0x180092b82  call    cs:__imp_free
0x180092b88  nop
0x180092b89  jmp     short loc_180092B0B
0x180092b8b  mov     r8, rbp; void *
0x180092b8e  mov     edx, [rdi+34h]; unsigned int
0x180092b91  mov     rcx, rdi; this
0x180092b94  call    ?SaveComponents@CMsmqVssWriter@@AEAAJKPEAX@Z; CMsmqVssWriter::SaveComponents(ulong,void *)
0x180092b99  mov     esi, eax
0x180092b9b  test    eax, eax
0x180092b9d  jns     short loc_180092BC3
0x180092b9f  mov     r8d, 0BF4h; unsigned __int16
0x180092ba5  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092bac  mov     ecx, eax; int
0x180092bae  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092bb3  nop
0x180092bb4  mov     rcx, rbx; Block
0x180092bb7  call    cs:__imp_free
0x180092bbd  nop
0x180092bbe  jmp     loc_180092B0B
0x180092bc3  mov     rdx, rbp; void *
0x180092bc6  mov     rcx, rdi; this
0x180092bc9  call    ?UpdateRestoreSeqID@CMsmqVssWriter@@AEAAJPEAX@Z; CMsmqVssWriter::UpdateRestoreSeqID(void *)
0x180092bce  mov     esi, eax
0x180092bd0  test    eax, eax
0x180092bd2  jns     short loc_180092BF8
0x180092bd4  mov     r8d, 0C08h; unsigned __int16
0x180092bda  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092be1  mov     ecx, eax; int
0x180092be3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092be8  nop
0x180092be9  mov     rcx, rbx; Block
0x180092bec  call    cs:__imp_free
0x180092bf2  nop
0x180092bf3  jmp     loc_180092B0B
0x180092bf8  mov     r8, [rdi+28h]; wchar_t *
0x180092bfc  test    r8, r8
0x180092bff  jz      short loc_180092C80
0x180092c01  mov     ebp, 14000A2h
0x180092c06  mov     r9d, ebp; unsigned int
0x180092c09  mov     rdx, [rdi+20h]; wchar_t *
0x180092c0d  mov     rcx, rdi; this
0x180092c10  call    ?AddRemoveRegCheckpoint@CMsmqVssWriter@@AEAAJPEB_W0K@Z; CMsmqVssWriter::AddRemoveRegCheckpoint(wchar_t const *,wchar_t const *,ulong)
0x180092c15  mov     esi, eax
0x180092c17  test    eax, eax
0x180092c19  jns     short loc_180092C3F
0x180092c1b  mov     r8d, 0C1Ch; unsigned __int16
0x180092c21  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092c28  mov     ecx, eax; int
0x180092c2a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092c2f  nop
0x180092c30  mov     rcx, rbx; Block
0x180092c33  call    cs:__imp_free
0x180092c39  nop
0x180092c3a  jmp     loc_180092B0B
0x180092c3f  test    rbx, rbx
0x180092c42  jz      short loc_180092C80
0x180092c44  mov     r9d, ebp; unsigned int
0x180092c47  mov     r8, rbx; wchar_t *
0x180092c4a  lea     rdx, [rsp+478h+var_438]; wchar_t *
0x180092c4f  mov     rcx, rdi; this
0x180092c52  call    ?AddRemoveRegCheckpoint@CMsmqVssWriter@@AEAAJPEB_W0K@Z; CMsmqVssWriter::AddRemoveRegCheckpoint(wchar_t const *,wchar_t const *,ulong)
0x180092c57  mov     edi, eax
0x180092c59  test    eax, eax
0x180092c5b  jns     short loc_180092C80
0x180092c5d  mov     r8d, 0C30h; unsigned __int16
0x180092c63  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180092c6a  mov     ecx, eax; int
0x180092c6c  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180092c71  nop
0x180092c72  mov     rcx, rbx; Block
0x180092c75  call    cs:__imp_free
0x180092c7b  nop
0x180092c7c  mov     eax, edi
0x180092c7e  jmp     short loc_180092C8C
0x180092c80  mov     rcx, rbx; Block
0x180092c83  call    cs:__imp_free
0x180092c89  nop
0x180092c8a  xor     eax, eax
0x180092c8c  mov     rcx, [rsp+478h+var_28]
0x180092c94  xor     rcx, rsp; StackCookie
0x180092c97  call    __security_check_cookie
0x180092c9c  mov     rbx, [rsp+478h+arg_18]
0x180092ca4  add     rsp, 460h
0x180092cab  pop     rdi
0x180092cac  pop     rsi
0x180092cad  pop     rbp
0x180092cae  retn
```
