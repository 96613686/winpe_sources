# CompletionRoutine

- ea: `0x180009920`
- end: `0x180009aa3`
- name: `CompletionRoutine`
- size: `387`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180009920`
- `0x18000be68`
- `0x180011230`
- `0x1800115a0`
- `0x1800115d0`
- `0x18002b0dc`
- `0x180034010`

## string_xrefs

- `0x180009991`: `CompletionRoutine called for protocol %x`
- `0x180009a49`: `The control protocol for %x on port %d, returned error %d`

## pseudocode

```c
_DWORD *__fastcall CompletionRoutine(__int64 a1, int a2, __int64 a3, int a4)
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
    if ( (byte_18004DF34 & 1) != 0 )
    {
      LOWORD(v11) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v11,
        L"CompletionRoutine called for protocol %x",
        *((unsigned int *)CpTable + 44 * CpIndexFromProtocol));
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v11);
    }
    result = (_DWORD *)((__int64 (__fastcall *)(__int64, __int64 *))xmmword_18004D480)(a1, &v10);
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
            if ( byte_18004DF33 < 0 )
            {
              LOWORD(v11) = 0;
              v9 = a4;
              FormatRRASErrorString(
                (wchar_t *)&v11,
                L"The control protocol for %x on port %d, returned error %d",
                *((unsigned int *)CpTable + 44 * CpIndexFromProtocol),
                v10,
                v9);
              if ( byte_18004DF33 < 0 )
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
0x180009920  mov     [rsp-8+arg_10], rbx
0x180009925  push    rbp
0x180009926  push    rsi
0x180009927  push    rdi
0x180009928  lea     rbp, [rsp-750h]
0x180009930  sub     rsp, 850h
0x180009937  mov     rax, cs:__security_cookie
0x18000993e  xor     rax, rsp
0x180009941  mov     [rbp+760h+var_20], rax
0x180009948  mov     rbx, rcx
0x18000994b  mov     [rsp+860h+var_830], 0
0x180009954  mov     ecx, edx
0x180009956  mov     esi, r9d
0x180009959  call    GetCpIndexFromProtocol
0x18000995e  xor     ecx, ecx
0x180009960  mov     edi, eax
0x180009962  mov     [rsp+860h+var_820], ecx
0x180009966  xor     edx, edx; Val
0x180009968  lea     rcx, [rsp+860h+var_81C]; void *
0x18000996d  mov     r8d, 7FCh; Size
0x180009973  call    memset_0
0x180009978  cmp     edi, 0FFFFFFFFh
0x18000997b  jz      loc_180009A80
0x180009981  test    cs:byte_18004DF34, 1
0x180009988  jz      short loc_1800099D5
0x18000998a  mov     r8, cs:CpTable
0x180009991  lea     rdx, aCompletionrout; "CompletionRoutine called for protocol %"...
0x180009998  imul    rcx, rdi, 0B0h
0x18000999f  xor     eax, eax
0x1800099a1  mov     word ptr [rsp+860h+var_820], ax
0x1800099a6  mov     r8d, [rcx+r8]
0x1800099aa  lea     rcx, [rsp+860h+var_820]
0x1800099af  call    FormatRRASErrorString
0x1800099b4  test    cs:byte_18004DF34, 1
0x1800099bb  jz      short loc_1800099D5
0x1800099bd  lea     r8, [rsp+860h+var_820]
0x1800099c2  lea     rdx, RasPppTraceInfo
0x1800099c9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800099d0  call    McTemplateU0z_EventWriteTransfer
0x1800099d5  mov     rax, qword ptr cs:xmmword_18004D480
0x1800099dc  lea     rdx, [rsp+860h+var_830]
0x1800099e1  mov     rcx, rbx
0x1800099e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099e9  test    eax, eax
0x1800099eb  jnz     loc_180009A80
0x1800099f1  mov     rcx, [rsp+860h+var_830]
0x1800099f6  call    GetPCBPointerFromhPort
0x1800099fb  mov     rbx, rax
0x1800099fe  test    rax, rax
0x180009a01  jz      short loc_180009A80
0x180009a03  mov     edx, edi
0x180009a05  mov     rcx, rax
0x180009a08  call    GetPointerToCPCB
0x180009a0d  test    rax, rax
0x180009a10  jz      short loc_180009A80
0x180009a12  test    esi, esi
0x180009a14  jz      short loc_180009A80
0x180009a16  mov     [rax+28h], esi
0x180009a19  cmp     cs:byte_18004DF33, 0
0x180009a20  jge     short loc_180009A76
0x180009a22  mov     r8, cs:CpTable
0x180009a29  lea     rcx, [rsp+860h+var_820]
0x180009a2e  mov     r9, [rsp+860h+var_830]
0x180009a33  xor     eax, eax
0x180009a35  imul    rdx, rdi, 0B0h
0x180009a3c  mov     word ptr [rsp+860h+var_820], ax
0x180009a41  mov     [rsp+860h+var_840], esi
0x180009a45  mov     r8d, [rdx+r8]
0x180009a49  lea     rdx, aTheControlProt; "The control protocol for %x on port %d,"...
0x180009a50  call    FormatRRASErrorString
0x180009a55  cmp     cs:byte_18004DF33, 0
0x180009a5c  jge     short loc_180009A76
0x180009a5e  lea     r8, [rsp+860h+var_820]
0x180009a63  lea     rdx, RasPppTraceError
0x180009a6a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009a71  call    McTemplateU0z_EventWriteTransfer
0x180009a76  mov     edx, edi
0x180009a78  mov     rcx, rbx
0x180009a7b  call    FsmClose
0x180009a80  mov     rcx, [rbp+760h+var_20]
0x180009a87  xor     rcx, rsp; StackCookie
0x180009a8a  call    __security_check_cookie
0x180009a8f  mov     rbx, [rsp+860h+arg_10]
0x180009a97  add     rsp, 850h
0x180009a9e  pop     rdi
0x180009a9f  pop     rsi
0x180009aa0  pop     rbp
0x180009aa1  retn
```
