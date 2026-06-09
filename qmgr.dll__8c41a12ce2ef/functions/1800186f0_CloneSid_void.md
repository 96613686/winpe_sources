# CloneSid(void *)

- ea: `0x1800186f0`
- end: `0x18001886e`
- name: `?CloneSid@@YAPEAXPEAX@Z`
- size: `382`
- prototype: `void *__fastcall(PSID pSourceSid)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016dac`
- `0x180019514`
- `0x18001a600`
- `0x180026414`
- `0x18003a860`

## callees

- `0x1800186f0`
- `0x18009e9c8`
- `0x1800a7558`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018764`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018764`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001871c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001871c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018840`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018840`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018736`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180018736`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018705`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018705`

## pseudocode

```c
void *__fastcall CloneSid(PSID pSourceSid)
{
  DWORD LengthSid; // edi
  void *v3; // rax
  void *v4; // rbx
  DWORD LastError; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-68h] BYREF
  __int128 v8; // [rsp+38h] [rbp-60h]
  int v9; // [rsp+48h] [rbp-50h]
  int v10; // [rsp+4Ch] [rbp-4Ch]
  int v11; // [rsp+50h] [rbp-48h]

  LengthSid = GetLengthSid(pSourceSid);
  v3 = HeapAlloc(hBitsHeap, 8u, LengthSid);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, LengthSid);
    v9 = -2147024882;
    v10 = 0;
    pExceptionObject = &ComError::`vftable';
    v11 = 1;
    v8 = 0;
    throw (ComError *)&pExceptionObject;
  }
  if ( !CopySid(LengthSid, v3, pSourceSid) )
  {
    if ( !HeapFree(hBitsHeap, 0, v4)
      && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids,
        v4,
        LastError);
    }
    v9 = -2147024882;
    v10 = 907;
    pExceptionObject = &ComError::`vftable';
    v11 = 1;
    v8 = 0;
    throw (ComError *)&pExceptionObject;
  }
  return v4;
}

```

## disassembly

```asm
0x1800186f0  mov     [rsp+arg_0], rbx
0x1800186f5  mov     [rsp+arg_8], rsi
0x1800186fa  push    rdi
0x1800186fb  sub     rsp, 90h
0x180018702  mov     rsi, rcx
0x180018705  call    cs:__imp_GetLengthSid
0x18001870b  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180018712  mov     edx, 8; dwFlags
0x180018717  mov     r8d, eax; dwBytes
0x18001871a  mov     edi, eax
0x18001871c  call    cs:__imp_HeapAlloc
0x180018722  mov     rbx, rax
0x180018725  test    rax, rax
0x180018728  jz      loc_1800187B0
0x18001872e  mov     r8, rsi; pSourceSid
0x180018731  mov     rdx, rax; pDestinationSid
0x180018734  mov     ecx, edi; nDestinationSidLength
0x180018736  call    cs:__imp_CopySid
0x18001873c  test    eax, eax
0x18001873e  jz      short loc_180018758
0x180018740  lea     r11, [rsp+98h+var_8]
0x180018748  mov     rax, rbx
0x18001874b  mov     rbx, [r11+10h]
0x18001874f  mov     rsi, [r11+18h]
0x180018753  mov     rsp, r11
0x180018756  pop     rdi
0x180018757  retn
0x180018758  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18001875f  mov     r8, rbx; lpMem
0x180018762  xor     edx, edx; dwFlags
0x180018764  call    cs:__imp_HeapFree
0x18001876a  test    eax, eax
0x18001876c  jz      loc_18001881F
0x180018772  xorps   xmm0, xmm0
0x180018775  mov     [rsp+98h+var_50], 8007000Eh
0x18001877d  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180018784  mov     [rsp+98h+var_4C], 38Bh
0x18001878c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018793  mov     [rsp+98h+pExceptionObject], rax
0x180018798  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001879d  mov     [rsp+98h+var_48], 1
0x1800187a5  movups  [rsp+98h+var_60], xmm0
0x1800187aa  call    _CxxThrowException_0
0x1800187b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187b7  lea     rax, WPP_GLOBAL_Control
0x1800187be  cmp     rcx, rax
0x1800187c1  jz      short loc_1800187E1
0x1800187c3  test    byte ptr [rcx+1Ch], 4
0x1800187c7  jz      short loc_1800187E1
0x1800187c9  mov     rcx, [rcx+10h]
0x1800187cd  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800187d4  mov     edx, 0Ah
0x1800187d9  mov     r9d, edi
0x1800187dc  call    WPP_SF_d
0x1800187e1  xorps   xmm0, xmm0
0x1800187e4  mov     [rsp+98h+var_50], 8007000Eh
0x1800187ec  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800187f3  mov     [rsp+98h+var_4C], 0
0x1800187fb  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180018802  mov     [rsp+98h+pExceptionObject], rax
0x180018807  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001880c  mov     [rsp+98h+var_48], 1
0x180018814  movups  [rsp+98h+var_60], xmm0
0x180018819  call    _CxxThrowException_0
0x18001881f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018826  lea     rax, WPP_GLOBAL_Control
0x18001882d  cmp     rcx, rax
0x180018830  jz      loc_180018772
0x180018836  test    byte ptr [rcx+1Ch], 4
0x18001883a  jz      loc_180018772
0x180018840  call    cs:__imp_GetLastError
0x180018846  mov     rcx, cs:WPP_GLOBAL_Control
0x18001884d  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180018854  mov     edx, 0Bh
0x180018859  mov     [rsp+98h+var_78], eax
0x18001885d  mov     r9, rbx
0x180018860  mov     rcx, [rcx+10h]
0x180018864  call    WPP_SF_qD
0x180018869  jmp     loc_180018772
```
