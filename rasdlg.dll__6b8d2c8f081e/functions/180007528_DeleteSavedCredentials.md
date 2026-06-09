# DeleteSavedCredentials

- ea: `0x180007528`
- end: `0x1800076d2`
- name: `DeleteSavedCredentials`
- size: `426`
- prototype: `__int64 __fastcall(__int64, HWND, __int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cbb0`
- `0x18000fdc8`

## callees

- `0x180007528`
- `0x18002cc5c`
- `0x180048b6c`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18000758f`
- `rtutils!TracePrintfExA` at `0x1800076ab`
- `rtutils!TracePrintfExA` at `0x18000758f`
- `rtutils!TracePrintfExA` at `0x1800076ab`

## string_xrefs

- `0x180007583`: `DeleteSavedCredentials: %d`
- `0x18000769f`: `DeleteSavedCredentials: RasSetCredentials=%d`

## pseudocode

```c
__int64 __fastcall DeleteSavedCredentials(__int64 a1, HWND a2, __int64 a3, int a4)
{
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-E0h]
  DWORD dwMessageId; // [rsp+40h] [rbp-C0h]
  int v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+54h] [rbp-ACh]
  _BYTE v13[1064]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v14[268]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(&v11, 0, 0x42Cu);
  dwMessageId = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DeleteSavedCredentials: %d", a4);
  memset_0(v13, 0, 0x424u);
  v11 = 1068;
  v12 = 7;
  if ( a4 && (v12 = 15, a3) )
  {
    memset_0(v14, 0, sizeof(v14));
    CopyRasCredentialsStruct(v14, &v11, 0);
    v9 = 1;
    LODWORD(result) = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *))(*(_QWORD *)a3 + 32LL))(
                        a3,
                        **(_QWORD **)(a1 + 32),
                        *(_QWORD *)(*(_QWORD *)(a1 + 440) + 8LL),
                        v14);
    if ( (int)result >= 0 )
    {
      result = 0;
      goto LABEL_10;
    }
    result = (unsigned __int16)result;
  }
  else
  {
    result = ((__int64 (__fastcall *)(_QWORD, _QWORD, int *, __int64))g_pRasSetCredentials)(
               **(_QWORD **)(a1 + 32),
               *(_QWORD *)(*(_QWORD *)(a1 + 440) + 8LL),
               &v11,
               1);
  }
  dwMessageId = result;
LABEL_10:
  if ( (_DWORD)result )
  {
    ErrorDlgUtil(a2, 0x157u, result, v9, 0x169u, 0xFAu);
    result = dwMessageId;
  }
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "DeleteSavedCredentials: RasSetCredentials=%d", result);
    return dwMessageId;
  }
  return result;
}

```

## disassembly

```asm
0x180007528  push    rbp
0x18000752a  push    rbx
0x18000752b  push    rsi
0x18000752c  push    rdi
0x18000752d  push    r14
0x18000752f  lea     rbp, [rsp-7C0h]
0x180007537  sub     rsp, 8C0h
0x18000753e  mov     rax, cs:__security_cookie
0x180007545  xor     rax, rsp
0x180007548  mov     [rbp+7E0h+var_30], rax
0x18000754f  mov     rsi, r8
0x180007552  mov     r14, rdx
0x180007555  mov     rdi, rcx
0x180007558  xor     edx, edx; Val
0x18000755a  mov     r8d, 42Ch; Size
0x180007560  lea     rcx, [rsp+8E0h+var_890]; void *
0x180007565  mov     ebx, r9d
0x180007568  call    memset_0
0x18000756d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180007573  mov     [rsp+8E0h+dwMessageId], 0
0x18000757b  cmp     ecx, 0FFFFFFFFh
0x18000757e  jz      short loc_180007595
0x180007580  mov     r9d, ebx
0x180007583  lea     r8, aDeletesavedcre_0; "DeleteSavedCredentials: %d"
0x18000758a  mov     edx, 0Ch; dwFlags
0x18000758f  call    cs:__imp_TracePrintfExA
0x180007595  xor     edx, edx; Val
0x180007597  lea     rcx, [rsp+8E0h+var_888]; void *
0x18000759c  mov     r8d, 424h; Size
0x1800075a2  call    memset_0
0x1800075a7  mov     [rsp+8E0h+var_890], 42Ch
0x1800075af  mov     [rsp+8E0h+var_88C], 7
0x1800075b7  test    ebx, ebx
0x1800075b9  jz      short loc_180007639
0x1800075bb  mov     [rsp+8E0h+var_88C], 0Fh
0x1800075c3  test    rsi, rsi
0x1800075c6  jz      short loc_180007639
0x1800075c8  xor     edx, edx; Val
0x1800075ca  lea     rcx, [rbp+7E0h+var_460]; void *
0x1800075d1  mov     r8d, 430h; Size
0x1800075d7  call    memset_0
0x1800075dc  xor     r8d, r8d
0x1800075df  lea     rdx, [rsp+8E0h+var_890]
0x1800075e4  lea     rcx, [rbp+7E0h+var_460]
0x1800075eb  call    CopyRasCredentialsStruct
0x1800075f0  mov     rax, [rsi]
0x1800075f3  lea     rcx, [rsp+8E0h+dwMessageId]
0x1800075f8  mov     r8, [rdi+1B8h]
0x1800075ff  lea     r9, [rbp+7E0h+var_460]
0x180007606  mov     rdx, [rdi+20h]
0x18000760a  mov     qword ptr [rsp+8E0h+var_8B8], rcx
0x18000760f  mov     rcx, rsi
0x180007612  mov     rax, [rax+20h]
0x180007616  mov     r8, [r8+8]
0x18000761a  mov     rdx, [rdx]
0x18000761d  mov     [rsp+8E0h+var_8C0], 1
0x180007625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000762a  test    eax, eax
0x18000762c  jns     short loc_180007633
0x18000762e  movzx   eax, ax
0x180007631  jmp     short loc_180007662
0x180007633  mov     eax, [rsp+8E0h+dwMessageId]
0x180007637  jmp     short loc_180007666
0x180007639  mov     rdx, [rdi+1B8h]
0x180007640  lea     r8, [rsp+8E0h+var_890]
0x180007645  mov     rcx, [rdi+20h]
0x180007649  mov     r9d, 1
0x18000764f  mov     rax, cs:g_pRasSetCredentials
0x180007656  mov     rdx, [rdx+8]
0x18000765a  mov     rcx, [rcx]
0x18000765d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007662  mov     [rsp+8E0h+dwMessageId], eax
0x180007666  test    eax, eax
0x180007668  jz      short loc_180007691
0x18000766a  mov     [rsp+8E0h+var_8B0], 0FAh; UINT
0x180007672  xor     r9d, r9d
0x180007675  mov     r8d, eax; dwMessageId
0x180007678  mov     [rsp+8E0h+var_8B8], 169h; UINT
0x180007680  mov     edx, 157h; uID
0x180007685  mov     rcx, r14; hWnd
0x180007688  call    ErrorDlgUtil
0x18000768d  mov     eax, [rsp+8E0h+dwMessageId]
0x180007691  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180007697  cmp     ecx, 0FFFFFFFFh
0x18000769a  jz      short loc_1800076B5
0x18000769c  mov     r9d, eax
0x18000769f  lea     r8, aDeletesavedcre; "DeleteSavedCredentials: RasSetCredentia"...
0x1800076a6  mov     edx, 0Ch; dwFlags
0x1800076ab  call    cs:__imp_TracePrintfExA
0x1800076b1  mov     eax, [rsp+8E0h+dwMessageId]
0x1800076b5  mov     rcx, [rbp+7E0h+var_30]
0x1800076bc  xor     rcx, rsp; StackCookie
0x1800076bf  call    __security_check_cookie
0x1800076c4  add     rsp, 8C0h
0x1800076cb  pop     r14
0x1800076cd  pop     rdi
0x1800076ce  pop     rsi
0x1800076cf  pop     rbx
0x1800076d0  pop     rbp
0x1800076d1  retn
```
