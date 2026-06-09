# LogPCWGenomeEvent(ushort const *,ushort const *,int,ushort const *,ushort const *)

- ea: `0x180008c38`
- end: `0x180008e56`
- name: `?LogPCWGenomeEvent@@YAHPEBG0H00@Z`
- size: `542`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lptstrFilename@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, const unsigned __int16 *@<r9>, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009200`

## callees

- `0x180008250`
- `0x1800084d8`
- `0x180008bb8`
- `0x180008c38`
- `0x18000e240`
- `0x1800191f0`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180008e23`
- `ntdll!EtwEventWriteNoRegistration` at `0x180008e23`

## string_xrefs

- `0x180008c7c`: `RecommendedLayer: %ws`

## pseudocode

```c
__int64 __fastcall LogPCWGenomeEvent(
        LPCWSTR lptstrFilename,
        const unsigned __int16 *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5)
{
  __int64 v8; // r8
  BOOL ExeInformation; // eax
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  int ExeVersionAsString; // eax
  unsigned __int16 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  unsigned __int8 v25[16]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h]
  int v28; // [rsp+4Ch] [rbp-B4h]
  unsigned __int16 *v29; // [rsp+50h] [rbp-B0h]
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  LPCWSTR v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+6Ch] [rbp-94h]
  const unsigned __int16 *v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  int *v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v40; // [rsp+90h] [rbp-70h]
  int v41; // [rsp+98h] [rbp-68h]
  int v42; // [rsp+9Ch] [rbp-64h]
  const unsigned __int16 *v43; // [rsp+A0h] [rbp-60h]
  int v44; // [rsp+A8h] [rbp-58h]
  int v45; // [rsp+ACh] [rbp-54h]
  unsigned __int16 v46[24]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[256]; // [rsp+100h] [rbp+0h] BYREF
  int v48; // [rsp+350h] [rbp+250h] BYREF

  v48 = a3;
  v25[0] = 0;
  AslLogCallPrintf(3, "LogPCWGenomeEvent", 1166, "RecommendedLayer: %ws", a2);
  ExeInformation = GetExeInformation(lptstrFilename, Buffer, v8, v25);
  v11 = ExeInformation;
  if ( v25[0] && ExeInformation || (unsigned int)LoadStringFromResourceFile(0x68u, Buffer, 256) )
  {
    ExeVersionAsString = GetExeVersionAsString(lptstrFilename, v46, v10);
    v13 = v46;
    if ( !ExeVersionAsString )
      v13 = L"0.0.0.0";
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( Buffer[v15] );
    v28 = 0;
    v27 = 2 * v15 + 2;
    v16 = -1;
    v26 = Buffer;
    do
      ++v16;
    while ( v13[v16] );
    v29 = v13;
    v30 = 2 * v16 + 2;
    v31 = 0;
    if ( lptstrFilename )
    {
      v17 = -1;
      do
        ++v17;
      while ( lptstrFilename[v17] );
      v18 = 2 * v17 + 2;
    }
    else
    {
      v18 = 0;
    }
    v32 = lptstrFilename;
    v33 = v18;
    v34 = 0;
    if ( a2 )
    {
      v19 = -1;
      do
        ++v19;
      while ( a2[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v20 = 0;
    }
    v36 = v20;
    v38 = &v48;
    v35 = a2;
    v37 = 0;
    v39 = 4;
    if ( a4 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a4[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v22 = 0;
    }
    v41 = v22;
    v40 = a4;
    v42 = 0;
    if ( a5 )
    {
      do
        ++v14;
      while ( a5[v14] );
      v23 = 2 * v14 + 2;
    }
    else
    {
      v23 = 0;
    }
    v44 = v23;
    v43 = a5;
    v45 = 0;
    EtwEventWriteNoRegistration(AE_LOG, AE_PCW_GENOME_LOG_INFO, 7, &v26);
    return 1;
  }
  return v11;
}

```

## disassembly

```asm
0x180008c38  mov     [rsp-8+arg_18], rbx
0x180008c3d  mov     [rsp-8+arg_10], r8d
0x180008c42  push    rbp
0x180008c43  push    rsi
0x180008c44  push    rdi
0x180008c45  push    r14
0x180008c47  push    r15
0x180008c49  lea     rbp, [rsp-210h]
0x180008c51  sub     rsp, 310h
0x180008c58  mov     rax, cs:__security_cookie
0x180008c5f  xor     rax, rsp
0x180008c62  mov     [rbp+230h+var_30], rax
0x180008c69  xor     r15d, r15d
0x180008c6c  mov     [rsp+330h+var_310], rdx
0x180008c71  mov     r14, r9
0x180008c74  mov     [rsp+330h+var_300], r15b
0x180008c79  mov     rsi, rdx
0x180008c7c  lea     r9, aRecommendedlay; "RecommendedLayer: %ws"
0x180008c83  mov     rdi, rcx
0x180008c86  lea     rdx, aLogpcwgenomeev; "LogPCWGenomeEvent"
0x180008c8d  lea     ecx, [r15+3]
0x180008c91  mov     r8d, 48Eh
0x180008c97  call    AslLogCallPrintf
0x180008c9c  lea     r9, [rsp+330h+var_300]; unsigned __int8 *
0x180008ca1  mov     rcx, rdi; pszPath
0x180008ca4  lea     rdx, [rbp+230h+Buffer]; unsigned __int16 *
0x180008ca8  call    ?GetExeInformation@@YAHPEBGPEAGKPEAE@Z; GetExeInformation(ushort const *,ushort *,ulong,uchar *)
0x180008cad  mov     ebx, eax
0x180008caf  cmp     [rsp+330h+var_300], r15b
0x180008cb4  jz      short loc_180008CBA
0x180008cb6  test    eax, eax
0x180008cb8  jnz     short loc_180008CD6
0x180008cba  mov     r8d, 100h; cchBufferMax
0x180008cc0  lea     rdx, [rbp+230h+Buffer]; lpBuffer
0x180008cc4  mov     ecx, 68h ; 'h'; uID
0x180008cc9  call    ?LoadStringFromResourceFile@@YAHIPEAGH@Z; LoadStringFromResourceFile(uint,ushort *,int)
0x180008cce  test    eax, eax
0x180008cd0  jz      loc_180008E2E
0x180008cd6  lea     rdx, [rbp+230h+var_260]; unsigned __int16 *
0x180008cda  mov     rcx, rdi; lptstrFilename
0x180008cdd  call    ?GetExeVersionAsString@@YAHPEBGPEAGK@Z; GetExeVersionAsString(ushort const *,ushort *,ulong)
0x180008ce2  test    eax, eax
0x180008ce4  lea     rcx, a0000; "0.0.0.0"
0x180008ceb  lea     rdx, [rbp+230h+var_260]
0x180008cef  cmovz   rdx, rcx
0x180008cf3  lea     r8, [rbp+230h+Buffer]
0x180008cf7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008cfb  mov     rax, rcx
0x180008cfe  inc     rax
0x180008d01  cmp     [r8+rax*2], r15w
0x180008d06  jnz     short loc_180008CFE
0x180008d08  lea     rax, ds:2[rax*2]
0x180008d10  mov     [rsp+330h+var_2E4], r15d
0x180008d15  lea     r8, [rbp+230h+Buffer]
0x180008d19  mov     [rsp+330h+var_2E8], eax
0x180008d1d  mov     rax, rcx
0x180008d20  mov     [rsp+330h+var_2F0], r8
0x180008d25  inc     rax
0x180008d28  cmp     [rdx+rax*2], r15w
0x180008d2d  jnz     short loc_180008D25
0x180008d2f  mov     [rsp+330h+var_2E0], rdx
0x180008d34  lea     rax, ds:2[rax*2]
0x180008d3c  mov     [rsp+330h+var_2D8], eax
0x180008d40  mov     [rsp+330h+var_2D4], r15d
0x180008d45  test    rdi, rdi
0x180008d48  jz      short loc_180008D61
0x180008d4a  mov     rax, rcx
0x180008d4d  inc     rax
0x180008d50  cmp     [rdi+rax*2], r15w
0x180008d55  jnz     short loc_180008D4D
0x180008d57  lea     rax, ds:2[rax*2]
0x180008d5f  jmp     short loc_180008D64
0x180008d61  mov     rax, r15
0x180008d64  mov     [rsp+330h+var_2D0], rdi
0x180008d69  mov     [rsp+330h+var_2C8], eax
0x180008d6d  mov     [rsp+330h+var_2C4], r15d
0x180008d72  test    rsi, rsi
0x180008d75  jz      short loc_180008D8E
0x180008d77  mov     rax, rcx
0x180008d7a  inc     rax
0x180008d7d  cmp     [rsi+rax*2], r15w
0x180008d82  jnz     short loc_180008D7A
0x180008d84  lea     rax, ds:2[rax*2]
0x180008d8c  jmp     short loc_180008D91
0x180008d8e  mov     rax, r15
0x180008d91  mov     [rsp+330h+var_2B8], eax
0x180008d95  lea     rax, [rbp+230h+arg_10]
0x180008d9c  mov     [rbp+230h+var_2B0], rax
0x180008da0  mov     [rsp+330h+var_2C0], rsi
0x180008da5  mov     [rsp+330h+var_2B4], r15d
0x180008daa  mov     [rbp+230h+var_2A8], 4
0x180008db2  test    r14, r14
0x180008db5  jz      short loc_180008DCE
0x180008db7  mov     rax, rcx
0x180008dba  inc     rax
0x180008dbd  cmp     [r14+rax*2], r15w
0x180008dc2  jnz     short loc_180008DBA
0x180008dc4  lea     rax, ds:2[rax*2]
0x180008dcc  jmp     short loc_180008DD1
0x180008dce  mov     rax, r15
0x180008dd1  mov     [rbp+230h+var_298], eax
0x180008dd4  mov     rax, [rbp+230h+arg_20]
0x180008ddb  mov     [rbp+230h+var_2A0], r14
0x180008ddf  mov     [rbp+230h+var_294], r15d
0x180008de3  test    rax, rax
0x180008de6  jz      short loc_180008DFC
0x180008de8  inc     rcx
0x180008deb  cmp     [rax+rcx*2], r15w
0x180008df0  jnz     short loc_180008DE8
0x180008df2  lea     rcx, ds:2[rcx*2]
0x180008dfa  jmp     short loc_180008DFF
0x180008dfc  mov     rcx, r15
0x180008dff  mov     [rbp+230h+var_288], ecx
0x180008e02  lea     r9, [rsp+330h+var_2F0]
0x180008e07  lea     rcx, AE_LOG
0x180008e0e  mov     [rbp+230h+var_290], rax
0x180008e12  mov     r8d, 7
0x180008e18  mov     [rbp+230h+var_284], r15d
0x180008e1c  lea     rdx, AE_PCW_GENOME_LOG_INFO
0x180008e23  call    cs:__imp_EtwEventWriteNoRegistration
0x180008e29  mov     ebx, 1
0x180008e2e  mov     eax, ebx
0x180008e30  mov     rcx, [rbp+230h+var_30]
0x180008e37  xor     rcx, rsp; StackCookie
0x180008e3a  call    __security_check_cookie
0x180008e3f  mov     rbx, [rsp+330h+arg_18]
0x180008e47  add     rsp, 310h
0x180008e4e  pop     r15
0x180008e50  pop     r14
0x180008e52  pop     rdi
0x180008e53  pop     rsi
0x180008e54  pop     rbp
0x180008e55  retn
```
