# CMsmqVssWriter::AddRemoveRegCheckpoint(wchar_t const *,wchar_t const *,ulong)

- ea: `0x18008da88`
- end: `0x18008dbd9`
- name: `?AddRemoveRegCheckpoint@CMsmqVssWriter@@AEAAJPEB_W0K@Z`
- size: `337`
- prototype: `int(CMsmqVssWriter *__hidden this, const wchar_t *, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800929fc`

## callees

- `0x18000cb80`
- `0x18002c61c`
- `0x18008d8c0`
- `0x18008d8e0`
- `0x18008da88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008daaf`
- `KERNEL32!GetLastError` at `0x18008dafe`
- `KERNEL32!GetLastError` at `0x18008daaf`
- `KERNEL32!GetLastError` at `0x18008dafe`
- `CLUSAPI!ClusterResourceControl` at `0x18008db71`
- `CLUSAPI!ClusterResourceControl` at `0x18008db71`
- `CLUSAPI!OpenCluster` at `0x18008da9f`
- `CLUSAPI!OpenCluster` at `0x18008da9f`
- `CLUSAPI!OpenClusterResource` at `0x18008daeb`
- `CLUSAPI!OpenClusterResource` at `0x18008daeb`

## string_xrefs

- `0x18008dad2`: `writer/mqwriter`
- `0x18008db1d`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::AddRemoveRegCheckpoint(
        const wchar_t **this,
        wchar_t *a2,
        const wchar_t *a3,
        DWORD a4)
{
  struct _HCLUSTER *v8; // rax
  signed int v9; // eax
  signed int v10; // ebx
  struct _HRESOURCE *v11; // rbx
  signed int LastError; // eax
  unsigned __int16 v13; // r8
  unsigned int v14; // eax
  signed int v15; // eax
  struct _HRESOURCE *v17; // [rsp+40h] [rbp-38h] BYREF
  struct _HCLUSTER *v18; // [rsp+48h] [rbp-30h] BYREF

  v8 = OpenCluster(0);
  v18 = v8;
  if ( v8 )
  {
    v11 = OpenClusterResource(v8, a3);
    v17 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 >= 0 )
        goto LABEL_12;
      v13 = 2060;
LABEL_11:
      LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", v13);
LABEL_12:
      CClusterResource::~CClusterResource((CClusterResource *)&v17);
      goto LABEL_16;
    }
    v14 = mqwcslen(this[4]);
    v15 = ClusterResourceControl(v11, 0, a4, a2, 2 * v14 + 2, 0, 0, 0);
    v10 = v15;
    if ( a4 == 20971682 )
    {
      if ( v15 == 183 )
        goto LABEL_15;
    }
    else if ( a4 == 20971686 && v15 == 2 )
    {
      goto LABEL_15;
    }
    if ( v15 )
    {
      if ( v15 > 0 )
        v10 = (unsigned __int16)v15 | 0x80070000;
      if ( v10 >= 0 )
        goto LABEL_12;
      v13 = 2080;
      goto LABEL_11;
    }
LABEL_15:
    CClusterResource::~CClusterResource((CClusterResource *)&v17);
    v10 = 0;
    goto LABEL_16;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
    LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x7F8u);
LABEL_16:
  CAutoCluster::~CAutoCluster((CAutoCluster *)&v18);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008da88  push    rbx
0x18008da8a  push    rbp
0x18008da8b  push    rsi
0x18008da8c  push    rdi
0x18008da8d  sub     rsp, 58h
0x18008da91  mov     edi, r9d
0x18008da94  mov     rbx, r8
0x18008da97  mov     rsi, rdx
0x18008da9a  mov     rbp, rcx
0x18008da9d  xor     ecx, ecx; lpszClusterName
0x18008da9f  call    cs:__imp_OpenCluster
0x18008daa5  mov     [rsp+78h+var_30], rax
0x18008daaa  test    rax, rax
0x18008daad  jnz     short loc_18008DAE5
0x18008daaf  call    cs:__imp_GetLastError
0x18008dab5  mov     ebx, eax
0x18008dab7  test    eax, eax
0x18008dab9  jle     short loc_18008DAC4
0x18008dabb  movzx   ebx, ax
0x18008dabe  or      ebx, 80070000h
0x18008dac4  test    ebx, ebx
0x18008dac6  jns     loc_18008DB94
0x18008dacc  mov     r8d, 7F8h; unsigned __int16
0x18008dad2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008dad9  mov     ecx, ebx; int
0x18008dadb  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008dae0  jmp     loc_18008DB94
0x18008dae5  mov     rdx, rbx; lpszResourceName
0x18008dae8  mov     rcx, rax; hCluster
0x18008daeb  call    cs:__imp_OpenClusterResource
0x18008daf1  mov     rbx, rax
0x18008daf4  mov     [rsp+78h+var_38], rax
0x18008daf9  test    rax, rax
0x18008dafc  jnz     short loc_18008DB38
0x18008dafe  call    cs:__imp_GetLastError
0x18008db04  mov     ebx, eax
0x18008db06  test    eax, eax
0x18008db08  jle     short loc_18008DB13
0x18008db0a  movzx   ebx, ax
0x18008db0d  or      ebx, 80070000h
0x18008db13  test    ebx, ebx
0x18008db15  jns     short loc_18008DB2C
0x18008db17  mov     r8d, 80Ch; unsigned __int16
0x18008db1d  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008db24  mov     ecx, ebx; int
0x18008db26  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008db2b  nop
0x18008db2c  lea     rcx, [rsp+78h+var_38]; this
0x18008db31  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x18008db36  jmp     short loc_18008DB94
0x18008db38  mov     rcx, [rbp+20h]; wchar_t *
0x18008db3c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18008db41  lea     eax, ds:2[rax*2]
0x18008db48  mov     [rsp+78h+lpBytesReturned], 0; lpBytesReturned
0x18008db51  mov     [rsp+78h+cbOutBufferSize], 0; cbOutBufferSize
0x18008db59  mov     [rsp+78h+lpOutBuffer], 0; lpOutBuffer
0x18008db62  mov     [rsp+78h+cbInBufferSize], eax; cbInBufferSize
0x18008db66  mov     r9, rsi; lpInBuffer
0x18008db69  mov     r8d, edi; dwControlCode
0x18008db6c  xor     edx, edx; hHostNode
0x18008db6e  mov     rcx, rbx; hResource
0x18008db71  call    cs:__imp_ClusterResourceControl
0x18008db77  mov     ebx, eax
0x18008db79  cmp     edi, 14000A2h
0x18008db7f  jnz     short loc_18008DBA9
0x18008db81  cmp     eax, 0B7h
0x18008db86  jnz     short loc_18008DBB6
0x18008db88  lea     rcx, [rsp+78h+var_38]; this
0x18008db8d  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x18008db92  xor     ebx, ebx
0x18008db94  lea     rcx, [rsp+78h+var_30]; this
0x18008db99  call    ??1CAutoCluster@@QEAA@XZ; CAutoCluster::~CAutoCluster(void)
0x18008db9e  mov     eax, ebx
0x18008dba0  add     rsp, 58h
0x18008dba4  pop     rdi
0x18008dba5  pop     rsi
0x18008dba6  pop     rbp
0x18008dba7  pop     rbx
0x18008dba8  retn
0x18008dba9  cmp     edi, 14000A6h
0x18008dbaf  jnz     short loc_18008DBB6
0x18008dbb1  cmp     eax, 2
0x18008dbb4  jz      short loc_18008DB88
0x18008dbb6  test    eax, eax
0x18008dbb8  jz      short loc_18008DB88
0x18008dbba  jle     short loc_18008DBC5
0x18008dbbc  movzx   ebx, ax
0x18008dbbf  or      ebx, 80070000h
0x18008dbc5  test    ebx, ebx
0x18008dbc7  jns     loc_18008DB2C
0x18008dbcd  mov     r8d, 820h
0x18008dbd3  jmp     loc_18008DB1D
```
