# LdrpResFileSize

- ea: `0x1800ade40`
- end: `0x1800adfd2`
- name: `LdrpResFileSize`
- size: `402`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800aa698`
- `0x1800af79c`

## callees

- `0x18006f0d0`
- `0x1800ade40`
- `0x1800ae518`
- `0x18015ed00`
- `0x180162810`

## string_xrefs

- `0x1800ade89`: `LdrResGetRCConfig Exit`
- `0x1800ade71`: `LdrResGetRCConfig Enter`

## pseudocode

```c
__int64 __fastcall LdrpResFileSize(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 result; // rax
  unsigned int v15; // edi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD v20[2]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v22; // [rsp+50h] [rbp-48h] BYREF
  __int128 v23; // [rsp+60h] [rbp-38h] BYREF
  __int64 v24; // [rsp+70h] [rbp-28h]

  v20[0] = 3145774;
  v24 = 0;
  v21[0] = 3014700;
  v20[1] = L"LdrResGetRCConfig Enter";
  v21[1] = L"LdrResGetRCConfig Exit";
  v22 = 0;
  v23 = 0;
  v10 = 2147353477;
  if ( (unsigned int)RtlGetCurrentServiceSessionId(a1, a2, a3, a4) )
    v11 = (__int64)NtCurrentPeb()->SharedData + 555;
  else
    v11 = 2147353477;
  v12 = 2147353476;
  if ( (*(_BYTE *)v11 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v7, v6, v8, v9) )
      v13 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v13 = 2147353476;
    LdrpTraceLoadMUIDll(v20, *(unsigned __int8 *)v13);
  }
  if ( a2 && (unsigned __int64)(a1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    result = NtQueryInformationFile(a1, &v22, &v23, 24, 5);
    v15 = result;
    if ( (int)result < 0 )
      return result;
    *a2 = *((_QWORD *)&v23 + 1);
  }
  else
  {
    v15 = -1073741811;
  }
  if ( (unsigned int)RtlGetCurrentServiceSessionId(v7, v6, v8, v9) )
    v10 = (__int64)NtCurrentPeb()->SharedData + 555;
  if ( (*(_BYTE *)v10 & 1) != 0 )
  {
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v17, v16, v18, v19) )
      v12 = (__int64)NtCurrentPeb()->SharedData + 554;
    LdrpTraceLoadMUIDll(v21, *(unsigned __int8 *)v12);
  }
  return v15;
}

```

## disassembly

```asm
0x1800ade40  mov     [rsp+arg_10], rbx
0x1800ade45  push    rbp
0x1800ade46  push    rsi
0x1800ade47  push    rdi
0x1800ade48  sub     rsp, 80h
0x1800ade4f  mov     rax, cs:__security_cookie
0x1800ade56  xor     rax, rsp
0x1800ade59  mov     [rsp+98h+var_20], rax
0x1800ade5e  xor     eax, eax
0x1800ade60  mov     [rsp+98h+var_68], 30002Eh
0x1800ade69  mov     [rsp+98h+var_28], rax
0x1800ade6e  xorps   xmm0, xmm0
0x1800ade71  lea     rax, aLdrresgetrccon_0; "LdrResGetRCConfig Enter"
0x1800ade78  mov     [rsp+98h+var_58], 2E002Ch
0x1800ade81  mov     [rsp+98h+var_60], rax
0x1800ade86  xorps   xmm1, xmm1
0x1800ade89  lea     rax, aLdrresgetrccon_1; "LdrResGetRCConfig Exit"
0x1800ade90  mov     rsi, rdx
0x1800ade93  mov     [rsp+98h+var_50], rax
0x1800ade98  mov     rdi, rcx
0x1800ade9b  movups  [rsp+98h+var_48], xmm0
0x1800adea0  movups  [rsp+98h+var_38], xmm1
0x1800adea5  call    RtlGetCurrentServiceSessionId
0x1800adeaa  mov     ebp, 7FFE0385h
0x1800adeaf  test    eax, eax
0x1800adeb1  jz      loc_1800ADFCA
0x1800adeb7  mov     rax, gs:60h
0x1800adec0  mov     rax, [rax+90h]
0x1800adec7  add     rax, 22Bh
0x1800adecd  test    byte ptr [rax], 1
0x1800aded0  mov     ebx, 7FFE0384h
0x1800aded5  jz      short loc_1800ADF08
0x1800aded7  call    RtlGetCurrentServiceSessionId
0x1800adedc  test    eax, eax
0x1800adede  jz      loc_1800ADFC2
0x1800adee4  mov     rax, gs:60h
0x1800adeed  mov     rcx, [rax+90h]
0x1800adef4  add     rcx, 22Ah
0x1800adefb  movzx   edx, byte ptr [rcx]
0x1800adefe  lea     rcx, [rsp+98h+var_68]
0x1800adf03  call    LdrpTraceLoadMUIDll
0x1800adf08  test    rsi, rsi
0x1800adf0b  jz      short loc_1800ADF47
0x1800adf0d  lea     rax, [rdi-1]
0x1800adf11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800adf15  ja      short loc_1800ADF47
0x1800adf17  mov     r9d, 18h
0x1800adf1d  mov     [rsp+98h+var_78], 5
0x1800adf25  lea     r8, [rsp+98h+var_38]
0x1800adf2a  mov     rcx, rdi
0x1800adf2d  lea     rdx, [rsp+98h+var_48]
0x1800adf32  call    NtQueryInformationFile
0x1800adf37  mov     edi, eax
0x1800adf39  test    eax, eax
0x1800adf3b  js      short loc_1800ADFA1
0x1800adf3d  mov     rax, qword ptr [rsp+98h+var_38+8]
0x1800adf42  mov     [rsi], rax
0x1800adf45  jmp     short loc_1800ADF4C
0x1800adf47  mov     edi, 0C000000Dh
0x1800adf4c  call    RtlGetCurrentServiceSessionId
0x1800adf51  test    eax, eax
0x1800adf53  jz      short loc_1800ADF6C
0x1800adf55  mov     rax, gs:60h
0x1800adf5e  mov     rbp, [rax+90h]
0x1800adf65  add     rbp, 22Bh
0x1800adf6c  test    byte ptr [rbp+0], 1
0x1800adf70  jz      short loc_1800ADF9F
0x1800adf72  call    RtlGetCurrentServiceSessionId
0x1800adf77  test    eax, eax
0x1800adf79  jz      short loc_1800ADF92
0x1800adf7b  mov     rax, gs:60h
0x1800adf84  mov     rbx, [rax+90h]
0x1800adf8b  add     rbx, 22Ah
0x1800adf92  movzx   edx, byte ptr [rbx]
0x1800adf95  lea     rcx, [rsp+98h+var_58]
0x1800adf9a  call    LdrpTraceLoadMUIDll
0x1800adf9f  mov     eax, edi
0x1800adfa1  mov     rcx, [rsp+98h+var_20]
0x1800adfa6  xor     rcx, rsp; StackCookie
0x1800adfa9  call    __security_check_cookie
0x1800adfae  mov     rbx, [rsp+98h+arg_10]
0x1800adfb6  add     rsp, 80h
0x1800adfbd  pop     rdi
0x1800adfbe  pop     rsi
0x1800adfbf  pop     rbp
0x1800adfc0  retn
0x1800adfc2  mov     rcx, rbx
0x1800adfc5  jmp     loc_1800ADEFB
0x1800adfca  mov     rax, rbp
0x1800adfcd  jmp     loc_1800ADECD
```
