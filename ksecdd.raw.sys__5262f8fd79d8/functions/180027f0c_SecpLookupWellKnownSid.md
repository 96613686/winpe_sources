# SecpLookupWellKnownSid

- ea: `0x180027f0c`
- end: `0x180028067`
- name: `SecpLookupWellKnownSid`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180004190`

## callees

- `0x180001a68`
- `0x180007ba8`
- `0x180007bd8`
- `0x180010a00`
- `0x180010d00`
- `0x180020e74`
- `0x180027f0c`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x180028022`
- `ntoskrnl!RtlLengthSid` at `0x180028022`

## pseudocode

```c
__int64 __fastcall SecpLookupWellKnownSid(int a1, void *a2, ULONG a3, ULONG *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // edi
  char *v13; // rbx
  ULONG v14; // eax
  ULONG v15; // esi
  _QWORD v16[70]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v16, 0, 0x1F8u);
  result = IsOkayToExec(v9, v8);
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 21, &WPP_ccfae065783230120d86f1ccbc684434_Traceguids);
    memset(v16, 0, 0xD0u);
    v16[0] = 5242920;
    LOWORD(v16[6]) = 0;
    v16[7] = 0;
    v16[5] = 24;
    LODWORD(v16[8]) = a1;
    v12 = CallSPM(v11, v16, v16);
    if ( v12 >= 0 )
      v12 = HIDWORD(v16[5]);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, &WPP_ccfae065783230120d86f1ccbc684434_Traceguids);
    if ( v12 >= 0 )
    {
      v13 = (char *)v16[9];
      if ( (unsigned __int64)(v16[9] - 216LL) <= 0x11F )
        v13 = (char *)v16 + v16[9];
      if ( v13 )
      {
        v14 = RtlLengthSid(v13);
        v15 = v14;
        if ( v14 > a3 )
          v12 = -1073741789;
        else
          memmove(a2, v13, v14);
        if ( a4 )
          *a4 = v15;
      }
      else
      {
        return (unsigned int)-1073741811;
      }
    }
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x180027f0c  push    rbp
0x180027f0e  push    rbx
0x180027f0f  push    rsi
0x180027f10  push    rdi
0x180027f11  push    r12
0x180027f13  push    r14
0x180027f15  push    r15
0x180027f17  lea     rbp, [rsp-120h]
0x180027f1f  sub     rsp, 220h
0x180027f26  mov     r15d, r8d
0x180027f29  mov     r12, rdx
0x180027f2c  mov     ebx, ecx
0x180027f2e  xor     edx, edx; Val
0x180027f30  mov     r8d, 1F8h; Size
0x180027f36  lea     rcx, [rsp+250h+var_230]; void *
0x180027f3b  mov     r14, r9
0x180027f3e  call    memset
0x180027f43  call    IsOkayToExec
0x180027f48  test    eax, eax
0x180027f4a  js      loc_180028054
0x180027f50  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f57  lea     rsi, WPP_GLOBAL_Control
0x180027f5e  cmp     rcx, rsi
0x180027f61  jz      short loc_180027F7F
0x180027f63  mov     eax, [rcx+2Ch]
0x180027f66  test    al, 4
0x180027f68  jz      short loc_180027F7F
0x180027f6a  mov     rcx, [rcx+18h]
0x180027f6e  lea     r8, WPP_ccfae065783230120d86f1ccbc684434_Traceguids
0x180027f75  mov     edx, 15h
0x180027f7a  call    WPP_SF_
0x180027f7f  xor     edx, edx; Val
0x180027f81  lea     rcx, [rsp+250h+var_230]; void *
0x180027f86  mov     r8d, 0D0h; Size
0x180027f8c  call    memset
0x180027f91  xor     eax, eax
0x180027f93  mov     [rsp+250h+var_230], 500028h
0x180027f9c  lea     r8, [rsp+250h+var_230]
0x180027fa1  mov     [rsp+250h+var_200], ax
0x180027fa6  lea     rdx, [rsp+250h+var_230]
0x180027fab  mov     [rsp+250h+var_1F8], rax
0x180027fb0  mov     [rsp+250h+var_208], 18h
0x180027fb9  mov     [rsp+250h+var_1F0], ebx
0x180027fbd  call    CallSPM
0x180027fc2  test    eax, eax
0x180027fc4  mov     edi, eax
0x180027fc6  cmovns  edi, dword ptr [rsp+250h+var_208+4]
0x180027fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fd2  cmp     rcx, rsi
0x180027fd5  jz      short loc_180027FF6
0x180027fd7  mov     eax, [rcx+2Ch]
0x180027fda  test    al, 4
0x180027fdc  jz      short loc_180027FF6
0x180027fde  mov     rcx, [rcx+18h]
0x180027fe2  lea     r8, WPP_ccfae065783230120d86f1ccbc684434_Traceguids
0x180027fe9  mov     edx, 16h
0x180027fee  mov     r9d, edi
0x180027ff1  call    WPP_SF_D
0x180027ff6  test    edi, edi
0x180027ff8  js      short loc_180028052
0x180027ffa  mov     rbx, [rsp+250h+Sid]
0x180027fff  lea     rax, [rbx-0D8h]
0x180028006  cmp     rax, 11Fh
0x18002800c  ja      short loc_180028013
0x18002800e  lea     rbx, [rsp+rbx+250h+var_230]
0x180028013  test    rbx, rbx
0x180028016  jnz     short loc_18002801F
0x180028018  mov     edi, 0C000000Dh
0x18002801d  jmp     short loc_180028052
0x18002801f  mov     rcx, rbx; Sid
0x180028022  call    cs:__imp_RtlLengthSid
0x180028029  nop     dword ptr [rax+rax+00h]
0x18002802e  mov     esi, eax
0x180028030  cmp     eax, r15d
0x180028033  ja      short loc_180028045
0x180028035  mov     r8d, esi; Size
0x180028038  mov     rdx, rbx; Src
0x18002803b  mov     rcx, r12; void *
0x18002803e  call    memmove
0x180028043  jmp     short loc_18002804A
0x180028045  mov     edi, 0C0000023h
0x18002804a  test    r14, r14
0x18002804d  jz      short loc_180028052
0x18002804f  mov     [r14], esi
0x180028052  mov     eax, edi
0x180028054  add     rsp, 220h
0x18002805b  pop     r15
0x18002805d  pop     r14
0x18002805f  pop     r12
0x180028061  pop     rdi
0x180028062  pop     rsi
0x180028063  pop     rbx
0x180028064  pop     rbp
0x180028065  retn
```
