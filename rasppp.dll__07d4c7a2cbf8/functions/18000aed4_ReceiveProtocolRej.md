# ReceiveProtocolRej

- ea: `0x18000aed4`
- end: `0x18000b161`
- name: `ReceiveProtocolRej`
- size: `653`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bfc0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000aed4`
- `0x18000df18`
- `0x18000e100`
- `0x18000e364`
- `0x18000f528`
- `0x180010cfc`
- `0x180011064`
- `0x180013490`
- `0x18002a138`

## string_xrefs

- `0x18000af1f`: `PPP Protocol Reject, Protocol = %x`
- `0x18000afcc`: `Protocol Rej silently discarded on port %d. Lcp not open`

## pseudocode

```c
__int64 __fastcall ReceiveProtocolRej(__int64 a1, unsigned __int8 *a2)
{
  __int64 result; // rax
  unsigned int v5; // esi
  __int64 v6; // r8
  int *PointerToCPCB; // rbx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // [rsp+30h] [rbp-828h] BYREF
  char v16[2044]; // [rsp+34h] [rbp-824h] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v15) = 0;
    FormatRRASErrorString(&v15, L"PPP Protocol Reject, Protocol = %x", 0);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v15);
  }
  result = a2[5];
  if ( (unsigned __int16)(result + (a2[4] << 8)) >= 6u )
  {
    result = GetCpIndexFromProtocol(a2[7] + (a2[6] << 8));
    v5 = result;
    if ( (_DWORD)result != -1 )
    {
      if ( !(_DWORD)result )
      {
        *(_DWORD *)(a1 + 1496) = 732;
        return NotifyCallerOfFailure(a1, 732);
      }
      if ( !*(_DWORD *)(a1 + 48) )
      {
        if ( byte_18004CF33 >= 0 )
          return result;
        v6 = *(_QWORD *)(a1 + 16);
        LOWORD(v15) = 0;
        result = FormatRRASErrorString(&v15, L"Protocol Rej silently discarded on port %d. Lcp not open", v6);
LABEL_11:
        if ( byte_18004CF33 < 0 )
          return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v15);
        return result;
      }
      if ( (unsigned int)result < (unsigned int)PppConfigInfo )
      {
        PointerToCPCB = (int *)GetPointerToCPCB(a1, (unsigned int)result);
        PointerToCPCB[10] = 733;
      }
      else
      {
        PointerToCPCB = (int *)(a1 + 1456);
        v5 = 0;
        *(_DWORD *)(a1 + 1496) = 917;
      }
      result = RemoveFromTimerQ(*(_DWORD *)(a1 + 64), PointerToCPCB[2], *((_DWORD *)CpTable + 44 * v5), 0, 0);
      v8 = *PointerToCPCB;
      if ( *PointerToCPCB <= 5 )
      {
        if ( v8 != 5 )
        {
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( !v10 )
                return result;
              v11 = v10 - 1;
              if ( !v11 )
                return result;
              if ( v11 == 1 )
              {
                result = FsmThisLayerFinished(a1, v5, 1);
                if ( (_DWORD)result )
                  *PointerToCPCB = 2;
                return result;
              }
            }
          }
LABEL_29:
          if ( byte_18004CF33 >= 0 )
            return result;
          LOWORD(v15) = 0;
          result = FormatRRASErrorString(
                     &v15,
                     L"Illegal transition->UnknownCode rcvd while in %hs state",
                     FsmStates[*PointerToCPCB]);
          goto LABEL_11;
        }
        goto LABEL_33;
      }
      v12 = v8 - 6;
      if ( !v12 || (v13 = v12 - 1) == 0 || (v14 = v13 - 1) == 0 )
      {
LABEL_33:
        result = FsmThisLayerFinished(a1, v5, 1);
        if ( (_DWORD)result )
          *PointerToCPCB = 3;
        return result;
      }
      if ( v14 != 1 )
        goto LABEL_29;
      result = FsmThisLayerDown(a1, v5);
      if ( (_DWORD)result )
      {
        PointerToCPCB[6] = dword_18004C9F8;
        PointerToCPCB[7] = dword_18004C9F4;
        result = FsmSendTermReq(a1, v5);
        *PointerToCPCB = 5;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000aed4  mov     [rsp+arg_10], rbx
0x18000aed9  push    rsi
0x18000aeda  push    rdi
0x18000aedb  push    r15
0x18000aedd  sub     rsp, 840h
0x18000aee4  mov     rax, cs:__security_cookie
0x18000aeeb  xor     rax, rsp
0x18000aeee  mov     [rsp+858h+var_28], rax
0x18000aef6  mov     rbx, rdx
0x18000aef9  mov     rdi, rcx
0x18000aefc  xor     eax, eax
0x18000aefe  lea     rcx, [rsp+858h+var_824]; void *
0x18000af03  xor     edx, edx; Val
0x18000af05  mov     [rsp+858h+var_828], eax
0x18000af09  mov     r8d, 7FCh; Size
0x18000af0f  call    memset_0
0x18000af14  test    cs:byte_18004CF34, 1
0x18000af1b  jz      short loc_18000AF59
0x18000af1d  xor     eax, eax
0x18000af1f  lea     rdx, aPppProtocolRej; "PPP Protocol Reject, Protocol = %x"
0x18000af26  xor     r8d, r8d
0x18000af29  mov     word ptr [rsp+858h+var_828], ax
0x18000af2e  lea     rcx, [rsp+858h+var_828]
0x18000af33  call    FormatRRASErrorString
0x18000af38  test    cs:byte_18004CF34, 1
0x18000af3f  jz      short loc_18000AF59
0x18000af41  lea     r8, [rsp+858h+var_828]
0x18000af46  lea     rdx, RasPppTraceInfo
0x18000af4d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000af54  call    McTemplateU0z_EventWriteTransfer
0x18000af59  movzx   edx, byte ptr [rbx+4]
0x18000af5d  mov     ecx, 100h
0x18000af62  movzx   eax, byte ptr [rbx+5]
0x18000af66  mov     r15d, 6
0x18000af6c  imul    edx, ecx
0x18000af6f  add     dx, ax
0x18000af72  cmp     dx, r15w
0x18000af76  jb      loc_18000B13D
0x18000af7c  movzx   eax, byte ptr [rbx+7]
0x18000af80  movzx   ecx, byte ptr [rbx+6]
0x18000af84  shl     ecx, 8
0x18000af87  add     ecx, eax
0x18000af89  call    GetCpIndexFromProtocol
0x18000af8e  mov     esi, eax
0x18000af90  cmp     eax, 0FFFFFFFFh
0x18000af93  jz      loc_18000B13D
0x18000af99  test    eax, eax
0x18000af9b  jnz     short loc_18000AFB5
0x18000af9d  mov     edx, 2DCh
0x18000afa2  mov     rcx, rdi
0x18000afa5  mov     [rdi+5D8h], edx
0x18000afab  call    NotifyCallerOfFailure
0x18000afb0  jmp     loc_18000B13D
0x18000afb5  cmp     dword ptr [rdi+30h], 0
0x18000afb9  jnz     short loc_18000B00E
0x18000afbb  cmp     cs:byte_18004CF33, 0
0x18000afc2  jge     loc_18000B13D
0x18000afc8  mov     r8, [rdi+10h]
0x18000afcc  lea     rdx, aProtocolRejSil; "Protocol Rej silently discarded on port"...
0x18000afd3  xor     eax, eax
0x18000afd5  mov     word ptr [rsp+858h+var_828], ax
0x18000afda  lea     rcx, [rsp+858h+var_828]
0x18000afdf  call    FormatRRASErrorString
0x18000afe4  cmp     cs:byte_18004CF33, 0
0x18000afeb  jge     loc_18000B13D
0x18000aff1  lea     r8, [rsp+858h+var_828]
0x18000aff6  lea     rdx, RasPppTraceError
0x18000affd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b004  call    McTemplateU0z_EventWriteTransfer
0x18000b009  jmp     loc_18000B13D
0x18000b00e  cmp     eax, dword ptr cs:PppConfigInfo
0x18000b014  jb      short loc_18000B028
0x18000b016  lea     rbx, [rdi+5B0h]
0x18000b01d  xor     esi, esi
0x18000b01f  mov     dword ptr [rbx+28h], 395h
0x18000b026  jmp     short loc_18000B03C
0x18000b028  mov     edx, eax
0x18000b02a  mov     rcx, rdi
0x18000b02d  call    GetPointerToCPCB
0x18000b032  mov     rbx, rax
0x18000b035  mov     dword ptr [rax+28h], 2DDh
0x18000b03c  mov     r8, cs:CpTable
0x18000b043  xor     r9d, r9d
0x18000b046  mov     ecx, esi
0x18000b048  imul    rdx, rcx, 0B0h
0x18000b04f  mov     ecx, [rdi+40h]
0x18000b052  mov     [rsp+858h+var_838], 0
0x18000b05a  mov     r8d, [rdx+r8]
0x18000b05e  mov     edx, [rbx+8]
0x18000b061  call    RemoveFromTimerQ
0x18000b066  mov     ecx, [rbx]
0x18000b068  cmp     ecx, 5
0x18000b06b  jg      short loc_18000B0B3
0x18000b06d  jz      loc_18000B123
0x18000b073  test    ecx, ecx
0x18000b075  jz      short loc_18000B0C7
0x18000b077  sub     ecx, 1
0x18000b07a  jz      short loc_18000B0C7
0x18000b07c  sub     ecx, 1
0x18000b07f  jz      loc_18000B13D
0x18000b085  sub     ecx, 1
0x18000b088  jz      loc_18000B13D
0x18000b08e  cmp     ecx, 1
0x18000b091  jnz     short loc_18000B0C7
0x18000b093  mov     r8d, ecx
0x18000b096  mov     edx, esi
0x18000b098  mov     rcx, rdi
0x18000b09b  call    FsmThisLayerFinished
0x18000b0a0  test    eax, eax
0x18000b0a2  jz      loc_18000B13D
0x18000b0a8  mov     dword ptr [rbx], 2
0x18000b0ae  jmp     loc_18000B13D
0x18000b0b3  sub     ecx, r15d
0x18000b0b6  jz      short loc_18000B123
0x18000b0b8  sub     ecx, 1
0x18000b0bb  jz      short loc_18000B123
0x18000b0bd  sub     ecx, 1
0x18000b0c0  jz      short loc_18000B123
0x18000b0c2  cmp     ecx, 1
0x18000b0c5  jz      short loc_18000B0F1
0x18000b0c7  cmp     cs:byte_18004CF33, 0
0x18000b0ce  jge     short loc_18000B13D
0x18000b0d0  xor     eax, eax
0x18000b0d2  lea     rdx, aIllegalTransit_0; "Illegal transition->UnknownCode rcvd wh"...
0x18000b0d9  mov     word ptr [rsp+858h+var_828], ax
0x18000b0de  lea     rax, FsmStates
0x18000b0e5  movsxd  r8, dword ptr [rbx]
0x18000b0e8  mov     r8, [rax+r8*8]
0x18000b0ec  jmp     loc_18000AFDA
0x18000b0f1  mov     edx, esi
0x18000b0f3  mov     rcx, rdi
0x18000b0f6  call    FsmThisLayerDown
0x18000b0fb  test    eax, eax
0x18000b0fd  jz      short loc_18000B13D
0x18000b0ff  mov     eax, cs:dword_18004C9F8
0x18000b105  mov     edx, esi
0x18000b107  mov     [rbx+18h], eax
0x18000b10a  mov     rcx, rdi
0x18000b10d  mov     eax, cs:dword_18004C9F4
0x18000b113  mov     [rbx+1Ch], eax
0x18000b116  call    FsmSendTermReq
0x18000b11b  mov     dword ptr [rbx], 5
0x18000b121  jmp     short loc_18000B13D
0x18000b123  mov     r8d, 1
0x18000b129  mov     edx, esi
0x18000b12b  mov     rcx, rdi
0x18000b12e  call    FsmThisLayerFinished
0x18000b133  test    eax, eax
0x18000b135  jz      short loc_18000B13D
0x18000b137  mov     dword ptr [rbx], 3
0x18000b13d  mov     rcx, [rsp+858h+var_28]
0x18000b145  xor     rcx, rsp; StackCookie
0x18000b148  call    __security_check_cookie
0x18000b14d  mov     rbx, [rsp+858h+arg_10]
0x18000b155  add     rsp, 840h
0x18000b15c  pop     r15
0x18000b15e  pop     rdi
0x18000b15f  pop     rsi
0x18000b160  retn
```
