# CxPlatSocketCreateUdp

- ea: `0x14003501c`
- end: `0x14003518a`
- name: `CxPlatSocketCreateUdp`
- size: `366`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140002e8c`
- `0x14002df00`

## callees

- `0x140001860`
- `0x14003501c`
- `0x14003b850`
- `0x14003c178`
- `0x14003c8e0`
- `0x14003ead8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400350be`
- `ntoskrnl!_snprintf_s` at `0x140035143`
- `ntoskrnl!_snprintf_s` at `0x1400350be`
- `ntoskrnl!_snprintf_s` at `0x140035143`

## string_xrefs

- `0x14003512a`: `[sock] Failed to create socket, status:%d`
- `0x1400350a9`: `[sock] Failed to create raw socket, status:%d`

## pseudocode

```c
__int64 __fastcall CxPlatSocketCreateUdp(__int64 a1, _QWORD *a2, __int64 *a3)
{
  char v4; // r15
  int v6; // ebp
  unsigned int Udp; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-B8h] BYREF

  v4 = a2[2] & 8;
  v6 = 0;
  while ( 1 )
  {
    Udp = SocketCreateUdp(a1, a2, a3);
    if ( (Udp & 0x80000000) != 0 )
      break;
    *(_BYTE *)(*a3 + 416) &= ~4u;
    if ( !v4 || !*(_QWORD *)(a1 + 64) )
      return Udp;
    Udp = -1073741637;
    *(_BYTE *)(*a3 + 416) &= ~4u;
    if ( byte_14005C48E < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[sock] Failed to create raw socket, status:%d", -1073741637);
      McTemplateU0s_EtwWriteTransfer(v9, QuicLogVerbose, DstBuf);
    }
    if ( *a2 && !(unsigned __int8)QuicAddrIsWildCard(*a2) || (a2[2] & 0x10) == 0 )
    {
      if ( (a2[2] & 0x10) != 0 )
        SocketDelete((PVOID)*a3);
      else
        return 0;
      return Udp;
    }
    SocketDelete((PVOID)*a3);
    if ( (unsigned int)++v6 >= 0x3E8 )
      return Udp;
  }
  if ( byte_14005C48E < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[sock] Failed to create socket, status:%d", Udp);
    McTemplateU0s_EtwWriteTransfer(v10, QuicLogVerbose, DstBuf);
  }
  return Udp;
}

```

## disassembly

```asm
0x14003501c  mov     [rsp+arg_18], rbx
0x140035021  push    rbp
0x140035022  push    rsi
0x140035023  push    rdi
0x140035024  push    r14
0x140035026  push    r15
0x140035028  sub     rsp, 0C0h
0x14003502f  mov     rax, cs:__security_cookie
0x140035036  xor     rax, rsp
0x140035039  mov     [rsp+0E8h+var_38], rax
0x140035041  mov     r15b, [rdx+10h]
0x140035045  mov     rdi, r8
0x140035048  and     r15b, 8
0x14003504c  mov     rsi, rdx
0x14003504f  xor     ebp, ebp
0x140035051  mov     r14, rcx
0x140035054  mov     r8, rdi
0x140035057  mov     rdx, rsi
0x14003505a  mov     rcx, r14
0x14003505d  call    SocketCreateUdp
0x140035062  mov     ebx, eax
0x140035064  test    eax, eax
0x140035066  js      loc_140035120
0x14003506c  mov     rcx, [rdi]
0x14003506f  and     byte ptr [rcx+1A0h], 0FBh
0x140035076  test    r15b, r15b
0x140035079  jz      loc_140035160
0x14003507f  cmp     qword ptr [r14+40h], 0
0x140035084  jz      loc_140035160
0x14003508a  mov     rax, [rdi]
0x14003508d  mov     ecx, 0C00000BBh
0x140035092  mov     ebx, ecx
0x140035094  and     byte ptr [rax+1A0h], 0FBh
0x14003509b  mov     al, cs:byte_14005C48E
0x1400350a1  test    al, al
0x1400350a3  jns     short loc_1400350DB
0x1400350a5  mov     [rsp+0E8h+var_C8], ecx
0x1400350a9  lea     r9, aSockFailedToCr; "[sock] Failed to create raw socket, sta"...
0x1400350b0  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x1400350b5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400350b9  mov     edx, 80h; SizeInBytes
0x1400350be  call    cs:__imp__snprintf_s
0x1400350c5  nop     dword ptr [rax+rax+00h]
0x1400350ca  lea     r8, [rsp+0E8h+DstBuf]
0x1400350cf  lea     rdx, QuicLogVerbose
0x1400350d6  call    McTemplateU0s_EtwWriteTransfer
0x1400350db  mov     rcx, [rsi]
0x1400350de  test    rcx, rcx
0x1400350e1  jz      short loc_1400350EC
0x1400350e3  call    QuicAddrIsWildCard
0x1400350e8  test    al, al
0x1400350ea  jz      short loc_14003510B
0x1400350ec  mov     eax, [rsi+10h]
0x1400350ef  test    al, 10h
0x1400350f1  jz      short loc_14003510B
0x1400350f3  mov     rcx, [rdi]; P
0x1400350f6  call    SocketDelete
0x1400350fb  inc     ebp
0x1400350fd  cmp     ebp, 3E8h
0x140035103  jb      loc_140035054
0x140035109  jmp     short loc_140035160
0x14003510b  mov     eax, [rsi+10h]
0x14003510e  test    al, 10h
0x140035110  jnz     short loc_140035116
0x140035112  xor     ebx, ebx
0x140035114  jmp     short loc_140035160
0x140035116  mov     rcx, [rdi]; P
0x140035119  call    SocketDelete
0x14003511e  jmp     short loc_140035160
0x140035120  mov     al, cs:byte_14005C48E
0x140035126  test    al, al
0x140035128  jns     short loc_140035160
0x14003512a  lea     r9, aSockFailedToCr_0; "[sock] Failed to create socket, status:"...
0x140035131  mov     [rsp+0E8h+var_C8], ebx
0x140035135  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140035139  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x14003513e  mov     edx, 80h; SizeInBytes
0x140035143  call    cs:__imp__snprintf_s
0x14003514a  nop     dword ptr [rax+rax+00h]
0x14003514f  lea     r8, [rsp+0E8h+DstBuf]
0x140035154  lea     rdx, QuicLogVerbose
0x14003515b  call    McTemplateU0s_EtwWriteTransfer
0x140035160  mov     eax, ebx
0x140035162  mov     rcx, [rsp+0E8h+var_38]
0x14003516a  xor     rcx, rsp; StackCookie
0x14003516d  call    __security_check_cookie
0x140035172  mov     rbx, [rsp+0E8h+arg_18]
0x14003517a  add     rsp, 0C0h
0x140035181  pop     r15
0x140035183  pop     r14
0x140035185  pop     rdi
0x140035186  pop     rsi
0x140035187  pop     rbp
0x140035188  retn
```
