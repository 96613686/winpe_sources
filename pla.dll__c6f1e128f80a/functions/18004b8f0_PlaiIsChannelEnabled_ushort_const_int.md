# PlaiIsChannelEnabled(ushort const *,int *)

- ea: `0x18004b8f0`
- end: `0x18004bb9e`
- name: `?PlaiIsChannelEnabled@@YAJPEBGPEAH@Z`
- size: `686`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004b488`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x18004b8f0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ba7f`
- `wevtapi!EvtOpenChannelConfig` at `0x18004b93b`
- `wevtapi!EvtOpenChannelConfig` at `0x18004b93b`
- `wevtapi!EvtClose` at `0x18004bb6f`
- `wevtapi!EvtClose` at `0x18004bb6f`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18004ba54`
- `wevtapi!EvtGetChannelConfigProperty` at `0x18004ba54`

## pseudocode

```c
__int64 __fastcall PlaiIsChannelEnabled(const unsigned __int16 *a1, int *a2)
{
  EVT_HANDLE v3; // rdi
  DWORD v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  DWORD LastError; // eax
  int v8; // eax
  __int64 v9; // rax
  int v11; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v12; // [rsp+78h] [rbp-88h] BYREF
  DWORD PropertyValueBufferUsed; // [rsp+80h] [rbp-80h] BYREF
  struct _EVT_VARIANT PropertyValueBuffer; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v15[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v16[64]; // [rsp+120h] [rbp+20h] BYREF

  PropertyValueBufferUsed = 0;
  PropertyValueBuffer = 0;
  v3 = EvtOpenChannelConfig(0, L"Microsoft-Windows-Diagnosis-PLA/Operational", 0);
  if ( v3 )
  {
    if ( EvtGetChannelConfigProperty(
           v3,
           EvtChannelConfigEnabled,
           0,
           0x10u,
           &PropertyValueBuffer,
           &PropertyValueBufferUsed) )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = PlaiHResultFromWin32(LastError);
      v5 = v8;
      if ( v8 < 0 )
      {
        v12 = 0;
        v11 = v8;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v16, 0x4000000000000800uLL);
          v9 = -1;
          do
            ++v9;
          while ( v16[v9] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v11,
            4,
            qword_180147320,
            1,
            &v12,
            4,
            "PlaiIsChannelEnabled",
            21);
        }
        goto LABEL_21;
      }
    }
    if ( PropertyValueBufferUsed == 16 && PropertyValueBuffer.Type == 13 )
      *a2 = PropertyValueBuffer.BooleanVal;
    else
      v5 = -2147467259;
LABEL_21:
    EvtClose(v3);
    return v5;
  }
  v4 = GetLastError();
  v5 = PlaiHResultFromWin32(v4);
  v11 = 0;
  v12 = v5;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v15, 0x4000000000000800uLL);
    v6 = -1;
    do
      ++v6;
    while ( v15[v6] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v12,
      4,
      qword_180147320,
      1,
      &v11,
      4,
      "PlaiIsChannelEnabled",
      21);
  }
  return v5;
}

```

## disassembly

```asm
0x18004b8f0  mov     [rsp-8+arg_0], rbx
0x18004b8f5  mov     [rsp-8+arg_10], rsi
0x18004b8fa  push    rbp
0x18004b8fb  push    rdi
0x18004b8fc  push    r14
0x18004b8fe  lea     rbp, [rsp-0B0h]
0x18004b906  sub     rsp, 1B0h
0x18004b90d  mov     rax, cs:__security_cookie
0x18004b914  xor     rax, rsp
0x18004b917  mov     [rbp+0C0h+var_20], rax
0x18004b91e  mov     rsi, rdx
0x18004b921  xorps   xmm0, xmm0
0x18004b924  xor     r14d, r14d
0x18004b927  lea     rdx, ChannelPath; "Microsoft-Windows-Diagnosis-PLA/Operati"...
0x18004b92e  xor     r8d, r8d; Flags
0x18004b931  mov     [rbp+0C0h+var_140], r14d
0x18004b935  xor     ecx, ecx; Session
0x18004b937  movups  xmmword ptr [rbp+0C0h+var_138], xmm0
0x18004b93b  call    cs:__imp_EvtOpenChannelConfig
0x18004b941  mov     rdi, rax
0x18004b944  test    rax, rax
0x18004b947  jnz     loc_18004BA34
0x18004b94d  call    cs:__imp_GetLastError
0x18004b953  mov     ecx, eax; unsigned int
0x18004b955  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004b95a  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004b961  mov     ebx, eax
0x18004b963  mov     [rsp+1C0h+var_150], r14d
0x18004b968  mov     [rsp+1C0h+var_148], eax
0x18004b96c  jz      loc_18004BB75
0x18004b972  mov     rdx, 4000000000000800h; unsigned __int64
0x18004b97c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004b983  jz      loc_18004BB75
0x18004b989  mov     rax, cs:qword_180169748
0x18004b990  and     rax, rdx
0x18004b993  cmp     cs:qword_180169748, rax
0x18004b99a  jnz     loc_18004BB75
0x18004b9a0  lea     rcx, [rbp+0C0h+var_120]; unsigned __int16 *
0x18004b9a4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004b9a9  lea     rcx, [rbp+0C0h+var_120]
0x18004b9ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b9b1  inc     rax
0x18004b9b4  cmp     [rcx+rax*2], r14w
0x18004b9b9  jnz     short loc_18004B9B1
0x18004b9bb  lea     ecx, [rax+rax]
0x18004b9be  add     rcx, 2
0x18004b9c2  lea     rax, [rbp+0C0h+var_120]
0x18004b9c6  mov     [rsp+1C0h+var_160], rcx
0x18004b9cb  lea     r9, [rsp+1C0h+var_148]
0x18004b9d0  mov     [rsp+1C0h+var_168], rax
0x18004b9d5  lea     rcx, [rsp+1C0h+var_150]
0x18004b9da  mov     [rsp+1C0h+var_170], 15h
0x18004b9e3  lea     rax, aPlaiischannele; "PlaiIsChannelEnabled"
0x18004b9ea  mov     [rsp+1C0h+var_178], rax
0x18004b9ef  lea     rdx, PLA_EVENT_ERROR
0x18004b9f6  mov     eax, 4
0x18004b9fb  mov     [rsp+1C0h+var_180], rax
0x18004ba00  mov     [rsp+1C0h+var_188], rcx
0x18004ba05  lea     rcx, qword_180147320
0x18004ba0c  mov     [rsp+1C0h+var_190], 1
0x18004ba15  mov     [rsp+1C0h+PropertyValueBufferUsed], rcx
0x18004ba1a  lea     r8d, [rax+1]
0x18004ba1e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004ba25  mov     [rsp+1C0h+PropertyValueBuffer], rax
0x18004ba2a  call    EventingWriteEvent
0x18004ba2f  jmp     loc_18004BB75
0x18004ba34  lea     rax, [rbp+0C0h+var_140]
0x18004ba38  mov     r9d, 10h; PropertyValueBufferSize
0x18004ba3e  mov     [rsp+1C0h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18004ba43  xor     r8d, r8d; Flags
0x18004ba46  lea     rax, [rbp+0C0h+var_138]
0x18004ba4a  xor     edx, edx; PropertyId
0x18004ba4c  mov     rcx, rdi; ChannelConfig
0x18004ba4f  mov     [rsp+1C0h+PropertyValueBuffer], rax; PropertyValueBuffer
0x18004ba54  call    cs:__imp_EvtGetChannelConfigProperty
0x18004ba5a  test    eax, eax
0x18004ba5c  jz      short loc_18004BA7F
0x18004ba5e  mov     ebx, r14d
0x18004ba61  cmp     [rbp+0C0h+var_140], 10h
0x18004ba65  jnz     loc_18004BB67
0x18004ba6b  cmp     [rbp+0C0h+var_138.Type], 0Dh
0x18004ba6f  jnz     loc_18004BB67
0x18004ba75  mov     eax, dword ptr [rbp+0C0h+var_138]
0x18004ba78  mov     [rsi], eax
0x18004ba7a  jmp     loc_18004BB6C
0x18004ba7f  call    cs:__imp_GetLastError
0x18004ba85  mov     ecx, eax; unsigned int
0x18004ba87  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004ba8c  mov     ebx, eax
0x18004ba8e  test    eax, eax
0x18004ba90  jns     short loc_18004BA61
0x18004ba92  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004ba99  mov     [rsp+1C0h+var_148], r14d
0x18004ba9e  mov     [rsp+1C0h+var_150], eax
0x18004baa2  jz      loc_18004BB6C
0x18004baa8  mov     rdx, 4000000000000800h; unsigned __int64
0x18004bab2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004bab9  jz      loc_18004BB6C
0x18004babf  mov     rax, cs:qword_180169748
0x18004bac6  and     rax, rdx
0x18004bac9  cmp     cs:qword_180169748, rax
0x18004bad0  jnz     loc_18004BB6C
0x18004bad6  lea     rcx, [rbp+0C0h+var_A0]; unsigned __int16 *
0x18004bada  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004badf  lea     rcx, [rbp+0C0h+var_A0]
0x18004bae3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004bae7  inc     rax
0x18004baea  cmp     [rcx+rax*2], r14w
0x18004baef  jnz     short loc_18004BAE7
0x18004baf1  lea     ecx, [rax+rax]
0x18004baf4  add     rcx, 2
0x18004baf8  lea     rax, [rbp+0C0h+var_A0]
0x18004bafc  mov     [rsp+1C0h+var_160], rcx
0x18004bb01  lea     r9, [rsp+1C0h+var_150]
0x18004bb06  mov     [rsp+1C0h+var_168], rax
0x18004bb0b  lea     rcx, [rsp+1C0h+var_148]
0x18004bb10  mov     [rsp+1C0h+var_170], 15h
0x18004bb19  lea     rax, aPlaiischannele; "PlaiIsChannelEnabled"
0x18004bb20  mov     [rsp+1C0h+var_178], rax
0x18004bb25  lea     rdx, PLA_EVENT_ERROR
0x18004bb2c  mov     eax, 4
0x18004bb31  mov     [rsp+1C0h+var_180], rax
0x18004bb36  mov     [rsp+1C0h+var_188], rcx
0x18004bb3b  lea     rcx, qword_180147320
0x18004bb42  mov     [rsp+1C0h+var_190], 1
0x18004bb4b  mov     [rsp+1C0h+PropertyValueBufferUsed], rcx
0x18004bb50  lea     r8d, [rax+1]
0x18004bb54  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004bb5b  mov     [rsp+1C0h+PropertyValueBuffer], rax
0x18004bb60  call    EventingWriteEvent
0x18004bb65  jmp     short loc_18004BB6C
0x18004bb67  mov     ebx, 80004005h
0x18004bb6c  mov     rcx, rdi; Object
0x18004bb6f  call    cs:__imp_EvtClose
0x18004bb75  mov     eax, ebx
0x18004bb77  mov     rcx, [rbp+0C0h+var_20]
0x18004bb7e  xor     rcx, rsp; StackCookie
0x18004bb81  call    __security_check_cookie
0x18004bb86  lea     r11, [rsp+1C0h+var_10]
0x18004bb8e  mov     rbx, [r11+20h]
0x18004bb92  mov     rsi, [r11+30h]
0x18004bb96  mov     rsp, r11
0x18004bb99  pop     r14
0x18004bb9b  pop     rdi
0x18004bb9c  pop     rbp
0x18004bb9d  retn
```
