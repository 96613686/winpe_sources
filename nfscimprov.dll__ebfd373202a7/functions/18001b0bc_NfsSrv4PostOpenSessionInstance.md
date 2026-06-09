# NfsSrv4PostOpenSessionInstance

- ea: `0x18001b0bc`
- end: `0x18001b21c`
- name: `NfsSrv4PostOpenSessionInstance`
- size: `352`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001a6d4`

## callees

- `0x18000be78`
- `0x180019818`
- `0x18001b0bc`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18001b178`
- `ntdll!RtlStringFromGUID` at `0x18001b178`
- `ntdll!RtlFreeUnicodeString` at `0x18001b1b6`
- `ntdll!RtlFreeUnicodeString` at `0x18001b1b6`

## pseudocode

```c
__int64 __fastcall NfsSrv4PostOpenSessionInstance(MI_Instance *self, __int64 a2)
{
  unsigned int v4; // ebx
  GUID v5; // xmm1
  char v6; // dl
  PWSTR Buffer; // [rsp+30h] [rbp-89h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+38h] [rbp-81h] BYREF
  GUID Guid; // [rsp+50h] [rbp-69h] BYREF
  MI_Instance selfa; // [rsp+60h] [rbp-59h] BYREF
  int v12; // [rsp+C0h] [rbp+7h]
  char v13; // [rsp+C4h] [rbp+Bh]
  __int64 v14; // [rsp+C8h] [rbp+Fh]
  char v15; // [rsp+D0h] [rbp+17h]
  int v16; // [rsp+D8h] [rbp+1Fh]
  char v17; // [rsp+DCh] [rbp+23h]
  int v18; // [rsp+E0h] [rbp+27h]
  char v19; // [rsp+E4h] [rbp+2Bh]
  int v20; // [rsp+E8h] [rbp+2Fh]
  char v21; // [rsp+ECh] [rbp+33h]

  memset_0(&selfa, 0, 0x90u);
  if ( self && self->ft )
  {
    v4 = ((__int64 (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
           self,
           &MSFT_NfsSession_rtti,
           &selfa);
    if ( !v4 )
    {
      v5 = *(GUID *)a2;
      v14 = *(_QWORD *)(a2 + 40);
      v4 = 1;
      v16 = *(_DWORD *)(a2 + 52);
      v18 = *(_DWORD *)(a2 + 56);
      v20 = *(_DWORD *)(a2 + 60);
      v12 = *(_DWORD *)(a2 + 48);
      v15 = 1;
      v17 = 1;
      v19 = 1;
      v21 = 1;
      v13 = 1;
      GuidString = 0;
      Guid = v5;
      if ( RtlStringFromGUID(&Guid, &GuidString) >= 0 )
      {
        Buffer = GuidString.Buffer;
        v4 = ((__int64 (__fastcall *)(MI_Instance *, _QWORD, PWSTR *, __int64, _DWORD))selfa.ft->SetElementAt)(
               &selfa,
               0,
               &Buffer,
               13,
               0);
        RtlFreeUnicodeString(&GuidString);
        if ( !v4 )
        {
          v6 = *(_BYTE *)(a2 + 16);
          Guid = *(GUID *)(a2 + 20);
          v4 = NfsSetNetworkNameOnInstance(&selfa, v6, &Guid);
          if ( !v4 )
            MI_Instance_Destruct(self);
        }
      }
      MI_Instance_Destruct(&selfa);
    }
  }
  else
  {
    return 4;
  }
  return v4;
}

```

## disassembly

```asm
0x18001b0bc  mov     [rsp-8+arg_10], rbx
0x18001b0c1  push    rbp
0x18001b0c2  push    rsi
0x18001b0c3  push    rdi
0x18001b0c4  lea     rbp, [rsp-47h]
0x18001b0c9  sub     rsp, 100h
0x18001b0d0  mov     rax, cs:__security_cookie
0x18001b0d7  xor     rax, rsp
0x18001b0da  mov     [rbp+57h+var_20], rax
0x18001b0de  mov     rdi, rdx
0x18001b0e1  mov     rsi, rcx
0x18001b0e4  xor     edx, edx; Val
0x18001b0e6  lea     rcx, [rbp+57h+self]; void *
0x18001b0ea  mov     r8d, 90h; Size
0x18001b0f0  call    memset_0
0x18001b0f5  test    rsi, rsi
0x18001b0f8  jz      loc_18001B1F6
0x18001b0fe  mov     rax, [rsi]
0x18001b101  test    rax, rax
0x18001b104  jz      loc_18001B1F6
0x18001b10a  mov     rax, [rax+18h]
0x18001b10e  lea     r8, [rbp+57h+self]
0x18001b112  lea     rdx, MSFT_NfsSession_rtti
0x18001b119  mov     rcx, rsi
0x18001b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b121  mov     ebx, eax
0x18001b123  test    eax, eax
0x18001b125  jnz     loc_18001B1FB
0x18001b12b  mov     rax, [rdi+28h]
0x18001b12f  lea     rdx, [rsp+110h+GuidString]; GuidString
0x18001b134  movups  xmm1, xmmword ptr [rdi]
0x18001b137  mov     [rbp+57h+var_48], rax
0x18001b13b  lea     rcx, [rbp+57h+Guid]; Guid
0x18001b13f  mov     eax, [rdi+34h]
0x18001b142  mov     ebx, 1
0x18001b147  mov     [rbp+57h+var_38], eax
0x18001b14a  xorps   xmm0, xmm0
0x18001b14d  mov     eax, [rdi+38h]
0x18001b150  mov     [rbp+57h+var_30], eax
0x18001b153  mov     eax, [rdi+3Ch]
0x18001b156  mov     [rbp+57h+var_28], eax
0x18001b159  mov     eax, [rdi+30h]
0x18001b15c  mov     [rbp+57h+var_50], eax
0x18001b15f  mov     [rbp+57h+var_40], bl
0x18001b162  mov     [rbp+57h+var_34], bl
0x18001b165  mov     [rbp+57h+var_2C], bl
0x18001b168  mov     [rbp+57h+var_24], bl
0x18001b16b  mov     [rbp+57h+var_4C], bl
0x18001b16e  movups  xmmword ptr [rsp+110h+GuidString.Length], xmm0
0x18001b173  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm1
0x18001b178  call    cs:__imp_RtlStringFromGUID
0x18001b17e  test    eax, eax
0x18001b180  js      short loc_18001B1EB
0x18001b182  mov     rax, [rbp+57h+GuidString.Buffer]
0x18001b186  lea     r9d, [rbx+0Ch]
0x18001b18a  mov     [rsp+110h+var_E0], rax
0x18001b18f  lea     r8, [rsp+110h+var_E0]
0x18001b194  mov     rax, [rbp+57h+self.ft]
0x18001b198  lea     rcx, [rbp+57h+self]
0x18001b19c  xor     edx, edx
0x18001b19e  mov     [rsp+110h+var_F0], 0
0x18001b1a6  mov     rax, [rax+50h]
0x18001b1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1af  lea     rcx, [rsp+110h+GuidString]; UnicodeString
0x18001b1b4  mov     ebx, eax
0x18001b1b6  call    cs:__imp_RtlFreeUnicodeString
0x18001b1bc  test    ebx, ebx
0x18001b1be  jnz     short loc_18001B1EB
0x18001b1c0  movups  xmm0, xmmword ptr [rdi+14h]
0x18001b1c4  mov     dl, [rdi+10h]
0x18001b1c7  lea     r8, [rbp+57h+Guid]
0x18001b1cb  lea     rcx, [rbp+57h+self]; self
0x18001b1cf  movdqu  xmmword ptr [rbp+57h+Guid.Data1], xmm0
0x18001b1d4  call    NfsSetNetworkNameOnInstance
0x18001b1d9  mov     ebx, eax
0x18001b1db  test    eax, eax
0x18001b1dd  jnz     short loc_18001B1EB
0x18001b1df  lea     rdx, [rbp+57h+self]
0x18001b1e3  mov     rcx, rsi; self
0x18001b1e6  call    MI_Instance_Destruct
0x18001b1eb  lea     rcx, [rbp+57h+self]; self
0x18001b1ef  call    MI_Instance_Destruct
0x18001b1f4  jmp     short loc_18001B1FB
0x18001b1f6  mov     ebx, 4
0x18001b1fb  mov     eax, ebx
0x18001b1fd  mov     rcx, [rbp+57h+var_20]
0x18001b201  xor     rcx, rsp; StackCookie
0x18001b204  call    __security_check_cookie
0x18001b209  mov     rbx, [rsp+110h+arg_10]
0x18001b211  add     rsp, 100h
0x18001b218  pop     rdi
0x18001b219  pop     rsi
0x18001b21a  pop     rbp
0x18001b21b  retn
```
