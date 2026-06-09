# CreateDxBltEvent(HWND__ * const,void * *,unsigned __int64 *)

- ea: `0x180013570`
- end: `0x1800136e6`
- name: `?CreateDxBltEvent@@YAJQEAUHWND__@@PEAPEAXPEA_K@Z`
- size: `374`
- prototype: `__int64 __fastcall(HWND, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf40`

## callees

- `0x180003370`
- `0x180003b30`
- `0x180009be0`
- `0x18000d0a0`
- `0x180013570`
- `0x180013b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013640`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180013640`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001365e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001365e`

## pseudocode

```c
__int64 __fastcall CreateDxBltEvent(HWND a1, void **a2, unsigned __int64 *a3)
{
  int v5; // eax
  struct _ACL *v6; // r15
  signed int v7; // ebx
  unsigned __int64 v8; // rsi
  HANDLE v9; // rdi
  unsigned int i; // r14d
  signed int LastError; // eax
  unsigned int v12; // edx
  int v13; // ecx
  struct _ACL *v15; // [rsp+30h] [rbp-49h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-41h] BYREF
  HWND v17; // [rsp+50h] [rbp-29h]
  WCHAR Name[32]; // [rsp+58h] [rbp-21h] BYREF

  v17 = a1;
  v15 = 0;
  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  v5 = DwmpAllocateSecurityDescriptor(&v15, 0x100002u);
  v6 = v15;
  v7 = v5;
  if ( v5 < 0 )
  {
    v12 = 364;
LABEL_19:
    v13 = v5;
LABEL_20:
    DoStackCaptureDirect(v13, v12);
  }
  else
  {
    v8 = 0;
    EventAttributes.lpSecurityDescriptor = v15;
    v9 = 0;
    for ( i = 0; !v9 && i < 0x7FFFFFFF; ++i )
    {
      v8 = (unsigned int)v17 | ((unsigned __int64)i << 32);
      v5 = StringCchPrintfW(Name, 0x1Fu, L"%s%I64x", L"DwmDxBltEvent_", v8);
      v7 = v5;
      if ( v5 < 0 )
      {
        v12 = 384;
        goto LABEL_19;
      }
      v9 = CreateEventW(&EventAttributes, 0, 0, Name);
      LastError = GetLastError();
      if ( v9 )
      {
        if ( LastError == 183 )
        {
          CloseHandle(v9);
          v9 = 0;
        }
      }
      else if ( LastError != 6 )
      {
        v7 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
        if ( v7 < 0 )
        {
          v12 = 405;
          v13 = v7;
          goto LABEL_20;
        }
      }
    }
    *a2 = v9;
    *a3 = v8;
  }
  if ( v6 )
    DwmpFreeSecurityDescriptor(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013570  mov     [rsp-8+arg_18], rbx
0x180013575  push    rbp
0x180013576  push    rsi
0x180013577  push    rdi
0x180013578  push    r12
0x18001357a  push    r13
0x18001357c  push    r14
0x18001357e  push    r15
0x180013580  lea     rbp, [rsp-27h]
0x180013585  sub     rsp, 0A0h
0x18001358c  mov     rax, cs:__security_cookie
0x180013593  xor     rax, rsp
0x180013596  mov     [rbp+57h+var_38], rax
0x18001359a  mov     r12, rdx
0x18001359d  mov     [rbp+57h+var_80], rcx
0x1800135a1  mov     edx, 100002h
0x1800135a6  mov     [rbp+57h+var_A0], 0
0x1800135ae  lea     rcx, [rbp+57h+var_A0]
0x1800135b2  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x1800135ba  mov     r13, r8
0x1800135bd  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], 0
0x1800135c5  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], 0
0x1800135cd  call    DwmpAllocateSecurityDescriptor
0x1800135d2  mov     r15, [rbp+57h+var_A0]
0x1800135d6  mov     ebx, eax
0x1800135d8  test    eax, eax
0x1800135da  js      loc_1800136A4
0x1800135e0  xor     esi, esi
0x1800135e2  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], r15
0x1800135e6  xor     edi, edi
0x1800135e8  xor     r14d, r14d
0x1800135eb  test    rdi, rdi
0x1800135ee  jnz     loc_18001369A
0x1800135f4  cmp     r14d, 7FFFFFFFh
0x1800135fb  jnb     loc_18001369A
0x180013601  mov     eax, dword ptr [rbp+57h+var_80]
0x180013604  lea     r9, aDwmdxbltevent; "DwmDxBltEvent_"
0x18001360b  mov     esi, r14d
0x18001360e  lea     r8, aSI64x; "%s%I64x"
0x180013615  shl     rsi, 20h
0x180013619  lea     edx, [rdi+1Fh]; unsigned __int64
0x18001361c  or      rsi, rax
0x18001361f  lea     rcx, [rbp+57h+Name]; unsigned __int16 *
0x180013623  mov     [rsp+0D0h+var_B0], rsi
0x180013628  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001362d  mov     ebx, eax
0x18001362f  test    eax, eax
0x180013631  js      short loc_180013693
0x180013633  lea     r9, [rbp+57h+Name]; lpName
0x180013637  xor     r8d, r8d; bInitialState
0x18001363a  xor     edx, edx; bManualReset
0x18001363c  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x180013640  call    cs:__imp_CreateEventW
0x180013646  mov     rdi, rax
0x180013649  call    cs:__imp_GetLastError
0x18001364f  test    rdi, rdi
0x180013652  jz      short loc_180013668
0x180013654  cmp     eax, 0B7h
0x180013659  jnz     short loc_180013682
0x18001365b  mov     rcx, rdi; hObject
0x18001365e  call    cs:__imp_CloseHandle
0x180013664  xor     edi, edi
0x180013666  jmp     short loc_180013682
0x180013668  cmp     eax, 6
0x18001366b  jz      short loc_180013682
0x18001366d  test    eax, eax
0x18001366f  jg      short loc_180013675
0x180013671  mov     ebx, eax
0x180013673  jmp     short loc_18001367E
0x180013675  movzx   ebx, ax
0x180013678  or      ebx, 80070000h
0x18001367e  test    ebx, ebx
0x180013680  js      short loc_18001368A
0x180013682  inc     r14d
0x180013685  jmp     loc_1800135EB
0x18001368a  mov     edx, 195h
0x18001368f  mov     ecx, ebx
0x180013691  jmp     short loc_1800136AB
0x180013693  mov     edx, 180h
0x180013698  jmp     short loc_1800136A9
0x18001369a  mov     [r12], rdi
0x18001369e  mov     [r13+0], rsi
0x1800136a2  jmp     short loc_1800136B0
0x1800136a4  mov     edx, 16Ch; unsigned int
0x1800136a9  mov     ecx, eax; int
0x1800136ab  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800136b0  test    r15, r15
0x1800136b3  jz      short loc_1800136BD
0x1800136b5  mov     rcx, r15
0x1800136b8  call    DwmpFreeSecurityDescriptor
0x1800136bd  mov     eax, ebx
0x1800136bf  mov     rcx, [rbp+57h+var_38]
0x1800136c3  xor     rcx, rsp; StackCookie
0x1800136c6  call    __security_check_cookie
0x1800136cb  mov     rbx, [rsp+0D0h+arg_18]
0x1800136d3  add     rsp, 0A0h
0x1800136da  pop     r15
0x1800136dc  pop     r14
0x1800136de  pop     r13
0x1800136e0  pop     r12
0x1800136e2  pop     rdi
0x1800136e3  pop     rsi
0x1800136e4  pop     rbp
0x1800136e5  retn
```
