# CompletionRoutine

- ea: `0x180009560`
- end: `0x1800096e2`
- name: `CompletionRoutine`
- size: `386`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180009560`
- `0x18000ba40`
- `0x180010cfc`
- `0x180011038`
- `0x180011064`
- `0x18002a138`
- `0x180033010`

## string_xrefs

- `0x1800095d1`: `CompletionRoutine called for protocol %x`
- `0x180009689`: `The control protocol for %x on port %d, returned error %d`

## pseudocode

```c
_DWORD *__fastcall CompletionRoutine(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  __int64 CpIndexFromProtocol; // rdi
  _DWORD *result; // rax
  _DWORD *v8; // rbx
  int v9; // [rsp+20h] [rbp-E0h]
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v12[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v10 = 0;
  CpIndexFromProtocol = (unsigned int)GetCpIndexFromProtocol(a2);
  v11 = 0;
  result = memset_0(v12, 0, sizeof(v12));
  if ( (_DWORD)CpIndexFromProtocol != -1 )
  {
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(
        &v11,
        L"CompletionRoutine called for protocol %x",
        *((unsigned int *)CpTable + 44 * CpIndexFromProtocol));
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v11);
    }
    result = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64 *))xmmword_18004C480)(a1, &v10);
    if ( !(_DWORD)result )
    {
      result = (_DWORD *)GetPCBPointerFromhPort(v10);
      v8 = result;
      if ( result )
      {
        result = (_DWORD *)GetPointerToCPCB(result, (unsigned int)CpIndexFromProtocol);
        if ( result )
        {
          if ( a4 )
          {
            result[10] = a4;
            if ( byte_18004CF33 < 0 )
            {
              LOWORD(v11) = 0;
              v9 = a4;
              FormatRRASErrorString(
                &v11,
                L"The control protocol for %x on port %d, returned error %d",
                *((unsigned int *)CpTable + 44 * CpIndexFromProtocol),
                v10,
                v9);
              if ( byte_18004CF33 < 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v11);
            }
            return (_DWORD *)FsmClose(v8, (unsigned int)CpIndexFromProtocol);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009560  mov     [rsp-8+arg_10], rbx
0x180009565  push    rbp
0x180009566  push    rsi
0x180009567  push    rdi
0x180009568  lea     rbp, [rsp-750h]
0x180009570  sub     rsp, 850h
0x180009577  mov     rax, cs:__security_cookie
0x18000957e  xor     rax, rsp
0x180009581  mov     [rbp+760h+var_20], rax
0x180009588  mov     rbx, rcx
0x18000958b  mov     [rsp+860h+var_830], 0
0x180009594  mov     ecx, edx
0x180009596  mov     esi, r9d
0x180009599  call    GetCpIndexFromProtocol
0x18000959e  xor     ecx, ecx
0x1800095a0  mov     edi, eax
0x1800095a2  mov     [rsp+860h+var_820], ecx
0x1800095a6  xor     edx, edx; Val
0x1800095a8  lea     rcx, [rsp+860h+var_81C]; void *
0x1800095ad  mov     r8d, 7FCh; Size
0x1800095b3  call    memset_0
0x1800095b8  cmp     edi, 0FFFFFFFFh
0x1800095bb  jz      loc_1800096C0
0x1800095c1  test    cs:byte_18004CF34, 1
0x1800095c8  jz      short loc_180009615
0x1800095ca  mov     r8, cs:CpTable
0x1800095d1  lea     rdx, aCompletionrout; "CompletionRoutine called for protocol %"...
0x1800095d8  imul    rcx, rdi, 0B0h
0x1800095df  xor     eax, eax
0x1800095e1  mov     word ptr [rsp+860h+var_820], ax
0x1800095e6  mov     r8d, [rcx+r8]
0x1800095ea  lea     rcx, [rsp+860h+var_820]
0x1800095ef  call    FormatRRASErrorString
0x1800095f4  test    cs:byte_18004CF34, 1
0x1800095fb  jz      short loc_180009615
0x1800095fd  lea     r8, [rsp+860h+var_820]
0x180009602  lea     rdx, RasPppTraceInfo
0x180009609  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009610  call    McTemplateU0z_EventWriteTransfer
0x180009615  mov     rax, qword ptr cs:xmmword_18004C480
0x18000961c  lea     rdx, [rsp+860h+var_830]
0x180009621  mov     rcx, rbx
0x180009624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009629  test    eax, eax
0x18000962b  jnz     loc_1800096C0
0x180009631  mov     rcx, [rsp+860h+var_830]
0x180009636  call    GetPCBPointerFromhPort
0x18000963b  mov     rbx, rax
0x18000963e  test    rax, rax
0x180009641  jz      short loc_1800096C0
0x180009643  mov     edx, edi
0x180009645  mov     rcx, rax
0x180009648  call    GetPointerToCPCB
0x18000964d  test    rax, rax
0x180009650  jz      short loc_1800096C0
0x180009652  test    esi, esi
0x180009654  jz      short loc_1800096C0
0x180009656  mov     [rax+28h], esi
0x180009659  cmp     cs:byte_18004CF33, 0
0x180009660  jge     short loc_1800096B6
0x180009662  mov     r8, cs:CpTable
0x180009669  lea     rcx, [rsp+860h+var_820]
0x18000966e  mov     r9, [rsp+860h+var_830]
0x180009673  xor     eax, eax
0x180009675  imul    rdx, rdi, 0B0h
0x18000967c  mov     word ptr [rsp+860h+var_820], ax
0x180009681  mov     [rsp+860h+var_840], esi
0x180009685  mov     r8d, [rdx+r8]
0x180009689  lea     rdx, aTheControlProt; "The control protocol for %x on port %d,"...
0x180009690  call    FormatRRASErrorString
0x180009695  cmp     cs:byte_18004CF33, 0
0x18000969c  jge     short loc_1800096B6
0x18000969e  lea     r8, [rsp+860h+var_820]
0x1800096a3  lea     rdx, RasPppTraceError
0x1800096aa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800096b1  call    McTemplateU0z_EventWriteTransfer
0x1800096b6  mov     edx, edi
0x1800096b8  mov     rcx, rbx
0x1800096bb  call    FsmClose
0x1800096c0  mov     rcx, [rbp+760h+var_20]
0x1800096c7  xor     rcx, rsp; StackCookie
0x1800096ca  call    __security_check_cookie
0x1800096cf  mov     rbx, [rsp+860h+arg_10]
0x1800096d7  add     rsp, 850h
0x1800096de  pop     rdi
0x1800096df  pop     rsi
0x1800096e0  pop     rbp
0x1800096e1  retn
```
