# sub_1800AFD0C

- ea: `0x1800afd0c`
- end: `0x1800b00a9`
- name: `sub_1800AFD0C`
- size: `925`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ca850`

## callees

- `0x180007874`
- `0x18000d210`
- `0x180013db0`
- `0x180039c14`
- `0x18003d3e0`
- `0x18003f28c`
- `0x1800afd0c`
- `0x1800cd268`
- `0x1800d59e8`
- `0x1800db7f4`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afdff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800affbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800affd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afdff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800affbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800affd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800afe84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0042`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800afe84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b0042`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800afe0b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800affc9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800afe0b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800affc9`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800aff3c`
- `MFPlat!MFGetConfigurationDWORD` at `0x1800aff3c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800afdb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800afe31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aff6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800affef`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800afdb0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800afe31`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800aff6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800affef`

## string_xrefs

- `0x1800afd20`: `CMFUrlmonByteStream::CreateInstance`
- `0x1800afe95`: `CMFUrlmonByteStream::CreateInstance`
- `0x1800b0053`: `CMFUrlmonByteStream::CreateInstance`

## pseudocode

```c
__int64 __fastcall sub_1800AFD0C(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v6; // rcx
  __int64 *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 *v10; // rsi
  DWORD v11; // r14d
  __int64 *v12; // rax
  __int64 *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  __int64 *v21; // rdi
  __int64 v22; // rax
  __int64 *v23; // rsi
  DWORD LastError; // r14d
  __int64 *Value; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v30; // [rsp+78h] [rbp+10h] BYREF

  v30 = a2;
  sub_180013DB0(&v30, "CMFUrlmonByteStream::CreateInstance", 93);
  if ( (unsigned __int8)byte_180124808 >= 0x20u )
    sub_180007874(*((_QWORD *)RequestContext + 2), 12, &stru_18010E588, 0);
  if ( (unsigned __int8)byte_18012480C >= 0x10u )
    sub_1800D59E8(*((_QWORD *)RequestContext + 22), 13, &stru_18010E588);
  LODWORD(v30) = 0;
  if ( a4 )
  {
    v17 = sub_1800CD268(5280);
    if ( v17 && (v19 = sub_1800DB7F4(v17, &v30), (v20 = v19) != 0) )
    {
      v8 = v30;
      if ( (int)v30 >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        sub_180039C14(v20 + 552, a3);
        LODWORD(v30) = 0;
        MFGetConfigurationDWORD(0, L"DisableUrlmonWorkaroundBuffer", &v30);
        *(_BYTE *)(v20 + 728) = (_DWORD)v30 == 0;
        *a4 = v20;
      }
      else if ( byte_180124808 )
      {
        v16 = 16;
        goto LABEL_52;
      }
    }
    else
    {
      v21 = (__int64 *)qword_180124958;
      v8 = -2147024882;
      if ( !qword_180124958 )
      {
        v22 = MFGetCallStackTracingWeakReference(v18);
        qword_180124958 = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = (__int64 *)qword_180124958;
        }
        else
        {
          v21 = &qword_180123EB0;
          qword_180124958 = (__int64)&qword_180123EB0;
        }
      }
      if ( *((_BYTE *)v21 + 8) )
      {
        v23 = v21 + 26;
        LastError = GetLastError();
        Value = (__int64 *)TlsGetValue(*((_DWORD *)v21 + 3));
        if ( Value )
        {
          v23 = Value;
        }
        else if ( !GetLastError() )
        {
          v26 = (__int64 *)qword_180124958;
          if ( !qword_180124958 )
          {
            v27 = MFGetCallStackTracingWeakReference(0);
            qword_180124958 = v27;
            if ( v27 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
            {
              v26 = (__int64 *)qword_180124958;
            }
            else
            {
              v26 = &qword_180123EB0;
              qword_180124958 = (__int64)&qword_180123EB0;
            }
          }
          v28 = (*(__int64 (__fastcall **)(__int64 *))*v26)(v26);
          if ( v28 )
            v23 = (__int64 *)v28;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v23 + 499) != -2147024882 )
          sub_18003D3E0(v23, "CMFUrlmonByteStream::CreateInstance", 103, 2147942414LL);
      }
      if ( byte_180124808 )
      {
        v16 = 15;
        goto LABEL_52;
      }
    }
  }
  else
  {
    v7 = (__int64 *)qword_180124958;
    v8 = -2147467261;
    if ( !qword_180124958 )
    {
      v9 = MFGetCallStackTracingWeakReference(v6);
      qword_180124958 = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v7 = (__int64 *)qword_180124958;
      }
      else
      {
        v7 = &qword_180123EB0;
        qword_180124958 = (__int64)&qword_180123EB0;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v10 = v7 + 26;
      v11 = GetLastError();
      v12 = (__int64 *)TlsGetValue(*((_DWORD *)v7 + 3));
      if ( v12 )
      {
        v10 = v12;
      }
      else if ( !GetLastError() )
      {
        v13 = (__int64 *)qword_180124958;
        if ( !qword_180124958 )
        {
          v14 = MFGetCallStackTracingWeakReference(0);
          qword_180124958 = v14;
          if ( v14 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
          {
            v13 = (__int64 *)qword_180124958;
          }
          else
          {
            v13 = &qword_180123EB0;
            qword_180124958 = (__int64)&qword_180123EB0;
          }
        }
        v15 = (*(__int64 (__fastcall **)(__int64 *))*v13)(v13);
        if ( v15 )
          v10 = (__int64 *)v15;
      }
      SetLastError(v11);
      if ( *((_DWORD *)v10 + 499) != -2147467261 )
        sub_18003D3E0(v10, "CMFUrlmonByteStream::CreateInstance", 100, 2147500035LL);
    }
    if ( byte_180124808 )
    {
      v16 = 14;
LABEL_52:
      sub_18003F28C(*((_QWORD *)RequestContext + 2), v16, &stru_18010E588, 0, v8);
    }
  }
  sub_18000D210(&v30);
  return v8;
}

```

## disassembly

```asm
0x1800afd0c  mov     [rsp+arg_8], rdx
0x1800afd11  push    rbx
0x1800afd12  push    rbp
0x1800afd13  push    rsi
0x1800afd14  push    rdi
0x1800afd15  push    r12
0x1800afd17  push    r14
0x1800afd19  sub     rsp, 38h
0x1800afd1d  mov     rbp, r8
0x1800afd20  lea     rdx, aCmfurlmonbytes_25; "CMFUrlmonByteStream::CreateInstance"
0x1800afd27  mov     r8d, 5Dh ; ']'
0x1800afd2d  lea     rcx, [rsp+68h+arg_8]
0x1800afd32  mov     rsi, r9
0x1800afd35  call    sub_180013DB0
0x1800afd3a  cmp     cs:byte_180124808, 20h ; ' '
0x1800afd41  lea     r12, stru_18010E588
0x1800afd48  jb      short loc_1800AFD65
0x1800afd4a  mov     rcx, cs:RequestContext
0x1800afd51  mov     edx, 0Ch
0x1800afd56  xor     r9d, r9d
0x1800afd59  mov     r8, r12
0x1800afd5c  mov     rcx, [rcx+10h]
0x1800afd60  call    sub_180007874
0x1800afd65  cmp     cs:byte_18012480C, 10h
0x1800afd6c  jb      short loc_1800AFD89
0x1800afd6e  mov     rcx, cs:RequestContext
0x1800afd75  mov     edx, 0Dh
0x1800afd7a  mov     r8, r12
0x1800afd7d  mov     rcx, [rcx+0B0h]
0x1800afd84  call    sub_1800D59E8
0x1800afd89  mov     dword ptr [rsp+68h+arg_8], 0
0x1800afd91  test    rsi, rsi
0x1800afd94  jnz     loc_1800AFEC1
0x1800afd9a  mov     rdi, cs:qword_180124958
0x1800afda1  mov     ebx, 80004003h
0x1800afda6  mov     ebp, 7F0h
0x1800afdab  test    rdi, rdi
0x1800afdae  jnz     short loc_1800AFDEE
0x1800afdb0  call    cs:MFGetCallStackTracingWeakReference
0x1800afdb6  mov     cs:qword_180124958, rax
0x1800afdbd  mov     rcx, rax
0x1800afdc0  test    rax, rax
0x1800afdc3  jz      short loc_1800AFDE0
0x1800afdc5  mov     rax, [rax]
0x1800afdc8  mov     edx, ebp
0x1800afdca  mov     rax, [rax+8]
0x1800afdce  call    j__guard_dispatch_icall
0x1800afdd3  test    eax, eax
0x1800afdd5  jz      short loc_1800AFDE0
0x1800afdd7  mov     rdi, cs:qword_180124958
0x1800afdde  jmp     short loc_1800AFDEE
0x1800afde0  lea     rdi, qword_180123EB0
0x1800afde7  mov     cs:qword_180124958, rdi
0x1800afdee  cmp     byte ptr [rdi+8], 0
0x1800afdf2  jz      loc_1800AFEAA
0x1800afdf8  lea     rsi, [rdi+0D0h]
0x1800afdff  call    cs:GetLastError
0x1800afe05  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800afe08  mov     r14d, eax
0x1800afe0b  call    cs:TlsGetValue
0x1800afe11  test    rax, rax
0x1800afe14  jz      short loc_1800AFE1B
0x1800afe16  mov     rsi, rax
0x1800afe19  jmp     short loc_1800AFE81
0x1800afe1b  call    cs:GetLastError
0x1800afe21  test    eax, eax
0x1800afe23  jnz     short loc_1800AFE81
0x1800afe25  mov     rcx, cs:qword_180124958
0x1800afe2c  test    rcx, rcx
0x1800afe2f  jnz     short loc_1800AFE6F
0x1800afe31  call    cs:MFGetCallStackTracingWeakReference
0x1800afe37  mov     cs:qword_180124958, rax
0x1800afe3e  mov     rcx, rax
0x1800afe41  test    rax, rax
0x1800afe44  jz      short loc_1800AFE61
0x1800afe46  mov     rax, [rax]
0x1800afe49  mov     edx, ebp
0x1800afe4b  mov     rax, [rax+8]
0x1800afe4f  call    j__guard_dispatch_icall
0x1800afe54  test    eax, eax
0x1800afe56  jz      short loc_1800AFE61
0x1800afe58  mov     rcx, cs:qword_180124958
0x1800afe5f  jmp     short loc_1800AFE6F
0x1800afe61  lea     rcx, qword_180123EB0
0x1800afe68  mov     cs:qword_180124958, rcx
0x1800afe6f  mov     rax, [rcx]
0x1800afe72  mov     rax, [rax]
0x1800afe75  call    j__guard_dispatch_icall
0x1800afe7a  test    rax, rax
0x1800afe7d  cmovnz  rsi, rax
0x1800afe81  mov     ecx, r14d; dwErrCode
0x1800afe84  call    cs:SetLastError
0x1800afe8a  cmp     [rsi+7CCh], ebx
0x1800afe90  jz      short loc_1800AFEAA
0x1800afe92  mov     r9d, ebx
0x1800afe95  lea     rdx, aCmfurlmonbytes_25; "CMFUrlmonByteStream::CreateInstance"
0x1800afe9c  mov     r8d, 64h ; 'd'
0x1800afea2  mov     rcx, rsi
0x1800afea5  call    sub_18003D3E0
0x1800afeaa  cmp     cs:byte_180124808, 1
0x1800afeb1  jb      loc_1800B0090
0x1800afeb7  mov     edx, 0Eh
0x1800afebc  jmp     loc_1800B0076
0x1800afec1  mov     ecx, 14A0h
0x1800afec6  call    sub_1800CD268
0x1800afecb  test    rax, rax
0x1800afece  jz      loc_1800AFF58
0x1800afed4  lea     rdx, [rsp+68h+arg_8]
0x1800afed9  mov     rcx, rax
0x1800afedc  call    sub_1800DB7F4
0x1800afee1  mov     rdi, rax
0x1800afee4  test    rax, rax
0x1800afee7  jz      short loc_1800AFF58
0x1800afee9  mov     ebx, dword ptr [rsp+68h+arg_8]
0x1800afeed  test    ebx, ebx
0x1800afeef  jns     short loc_1800AFF08
0x1800afef1  cmp     cs:byte_180124808, 1
0x1800afef8  jb      loc_1800B0090
0x1800afefe  mov     edx, 10h
0x1800aff03  jmp     loc_1800B0076
0x1800aff08  mov     rax, [rax]
0x1800aff0b  mov     rcx, rdi
0x1800aff0e  mov     rax, [rax+8]
0x1800aff12  call    j__guard_dispatch_icall
0x1800aff17  lea     rcx, [rdi+228h]
0x1800aff1e  mov     rdx, rbp
0x1800aff21  call    sub_180039C14
0x1800aff26  lea     r8, [rsp+68h+arg_8]
0x1800aff2b  mov     dword ptr [rsp+68h+arg_8], 0
0x1800aff33  lea     rdx, aDisableurlmonw; "DisableUrlmonWorkaroundBuffer"
0x1800aff3a  xor     ecx, ecx
0x1800aff3c  call    cs:MFGetConfigurationDWORD
0x1800aff42  cmp     dword ptr [rsp+68h+arg_8], 0
0x1800aff47  setz    al
0x1800aff4a  mov     [rdi+2D8h], al
0x1800aff50  mov     [rsi], rdi
0x1800aff53  jmp     loc_1800B0090
0x1800aff58  mov     rdi, cs:qword_180124958
0x1800aff5f  mov     ebx, 8007000Eh
0x1800aff64  mov     ebp, 7F0h
0x1800aff69  test    rdi, rdi
0x1800aff6c  jnz     short loc_1800AFFAC
0x1800aff6e  call    cs:MFGetCallStackTracingWeakReference
0x1800aff74  mov     cs:qword_180124958, rax
0x1800aff7b  mov     rcx, rax
0x1800aff7e  test    rax, rax
0x1800aff81  jz      short loc_1800AFF9E
0x1800aff83  mov     rax, [rax]
0x1800aff86  mov     edx, ebp
0x1800aff88  mov     rax, [rax+8]
0x1800aff8c  call    j__guard_dispatch_icall
0x1800aff91  test    eax, eax
0x1800aff93  jz      short loc_1800AFF9E
0x1800aff95  mov     rdi, cs:qword_180124958
0x1800aff9c  jmp     short loc_1800AFFAC
0x1800aff9e  lea     rdi, qword_180123EB0
0x1800affa5  mov     cs:qword_180124958, rdi
0x1800affac  cmp     byte ptr [rdi+8], 0
0x1800affb0  jz      loc_1800B0068
0x1800affb6  lea     rsi, [rdi+0D0h]
0x1800affbd  call    cs:GetLastError
0x1800affc3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800affc6  mov     r14d, eax
0x1800affc9  call    cs:TlsGetValue
0x1800affcf  test    rax, rax
0x1800affd2  jz      short loc_1800AFFD9
0x1800affd4  mov     rsi, rax
0x1800affd7  jmp     short loc_1800B003F
0x1800affd9  call    cs:GetLastError
0x1800affdf  test    eax, eax
0x1800affe1  jnz     short loc_1800B003F
0x1800affe3  mov     rcx, cs:qword_180124958
0x1800affea  test    rcx, rcx
0x1800affed  jnz     short loc_1800B002D
0x1800affef  call    cs:MFGetCallStackTracingWeakReference
0x1800afff5  mov     cs:qword_180124958, rax
0x1800afffc  mov     rcx, rax
0x1800affff  test    rax, rax
0x1800b0002  jz      short loc_1800B001F
0x1800b0004  mov     rax, [rax]
0x1800b0007  mov     edx, ebp
0x1800b0009  mov     rax, [rax+8]
0x1800b000d  call    j__guard_dispatch_icall
0x1800b0012  test    eax, eax
0x1800b0014  jz      short loc_1800B001F
0x1800b0016  mov     rcx, cs:qword_180124958
0x1800b001d  jmp     short loc_1800B002D
0x1800b001f  lea     rcx, qword_180123EB0
0x1800b0026  mov     cs:qword_180124958, rcx
0x1800b002d  mov     rax, [rcx]
0x1800b0030  mov     rax, [rax]
0x1800b0033  call    j__guard_dispatch_icall
0x1800b0038  test    rax, rax
0x1800b003b  cmovnz  rsi, rax
0x1800b003f  mov     ecx, r14d; dwErrCode
0x1800b0042  call    cs:SetLastError
0x1800b0048  cmp     [rsi+7CCh], ebx
0x1800b004e  jz      short loc_1800B0068
0x1800b0050  mov     r9d, ebx
0x1800b0053  lea     rdx, aCmfurlmonbytes_25; "CMFUrlmonByteStream::CreateInstance"
0x1800b005a  mov     r8d, 67h ; 'g'
0x1800b0060  mov     rcx, rsi
0x1800b0063  call    sub_18003D3E0
0x1800b0068  cmp     cs:byte_180124808, 1
0x1800b006f  jb      short loc_1800B0090
0x1800b0071  mov     edx, 0Fh
0x1800b0076  mov     rcx, cs:RequestContext
0x1800b007d  xor     r9d, r9d
0x1800b0080  mov     r8, r12
0x1800b0083  mov     [rsp+68h+var_48], ebx
0x1800b0087  mov     rcx, [rcx+10h]
0x1800b008b  call    sub_18003F28C
0x1800b0090  lea     rcx, [rsp+68h+arg_8]
0x1800b0095  call    sub_18000D210
0x1800b009a  mov     eax, ebx
0x1800b009c  add     rsp, 38h
0x1800b00a0  pop     r14
0x1800b00a2  pop     r12
0x1800b00a4  pop     rdi
0x1800b00a5  pop     rsi
0x1800b00a6  pop     rbp
0x1800b00a7  pop     rbx
0x1800b00a8  retn
```
