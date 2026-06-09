# EvtTraceScope::~EvtTraceScope(void)

- ea: `0x180011d5c`
- end: `0x180011e09`
- name: `??1EvtTraceScope@@QEAA@XZ`
- size: `173`
- prototype: `void __fastcall(EvtTraceScope *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012ed4`
- `0x180016b88`
- `0x180016ca8`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`

## callees

- `0x1800022e0`
- `0x1800097fc`
- `0x180011d5c`

## pseudocode

```c
void __fastcall EvtTraceScope::~EvtTraceScope(EvtTraceScope *this)
{
  int *v1; // rax
  int v2; // edx
  const char *v3; // rax
  __int64 v4; // rcx
  int v5; // ecx
  int v6; // [rsp+30h] [rbp-48h] BYREF
  char v7[16]; // [rsp+38h] [rbp-40h] BYREF
  const char *v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+50h] [rbp-28h]
  int v10; // [rsp+54h] [rbp-24h]
  int *v11; // [rsp+58h] [rbp-20h]
  __int64 v12; // [rsp+60h] [rbp-18h]

  v1 = (int *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    v2 = *v1;
    if ( *v1 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
    {
      v3 = *(const char **)this;
      v6 = v2;
      if ( v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( v3[v4] );
        v5 = v4 + 1;
      }
      else
      {
        v3 = "NULL";
        v5 = 5;
      }
      v8 = v3;
      v9 = v5;
      v11 = &v6;
      v10 = 0;
      v12 = 4;
      McGenEventWrite_EventWriteTransfer(
        WP_ENROLLMENT_API_PROVIDER_Context,
        LeavingScopeWithFailedResultEvent,
        0,
        3,
        v7);
    }
  }
}

```

## disassembly

```asm
0x180011d5c  sub     rsp, 78h
0x180011d60  mov     rax, cs:__security_cookie
0x180011d67  xor     rax, rsp
0x180011d6a  mov     [rsp+78h+var_10], rax
0x180011d6f  mov     rax, [rcx+8]
0x180011d73  xor     r8d, r8d
0x180011d76  test    rax, rax
0x180011d79  jz      short loc_180011DF7
0x180011d7b  mov     edx, [rax]
0x180011d7d  test    edx, edx
0x180011d7f  jns     short loc_180011DF7
0x180011d81  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x180011d88  jz      short loc_180011DF7
0x180011d8a  mov     rax, [rcx]
0x180011d8d  mov     [rsp+78h+var_48], edx
0x180011d91  test    rax, rax
0x180011d94  jz      short loc_180011DA7
0x180011d96  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180011d9a  inc     rcx
0x180011d9d  cmp     [rax+rcx], r8b
0x180011da1  jnz     short loc_180011D9A
0x180011da3  inc     ecx
0x180011da5  jmp     short loc_180011DB3
0x180011da7  lea     rax, aNull; "NULL"
0x180011dae  mov     ecx, 5
0x180011db3  mov     [rsp+78h+var_30], rax
0x180011db8  lea     rdx, LeavingScopeWithFailedResultEvent
0x180011dbf  lea     rax, [rsp+78h+var_48]
0x180011dc4  mov     [rsp+78h+var_28], ecx
0x180011dc8  mov     [rsp+78h+var_20], rax
0x180011dcd  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180011dd4  lea     rax, [rsp+78h+var_40]
0x180011dd9  mov     [rsp+78h+var_24], r8d
0x180011dde  mov     r9d, 3
0x180011de4  mov     [rsp+78h+var_58], rax
0x180011de9  mov     [rsp+78h+var_18], 4
0x180011df2  call    McGenEventWrite_EventWriteTransfer
0x180011df7  mov     rcx, [rsp+78h+var_10]
0x180011dfc  xor     rcx, rsp; StackCookie
0x180011dff  call    __security_check_cookie
0x180011e04  add     rsp, 78h
0x180011e08  retn
```
