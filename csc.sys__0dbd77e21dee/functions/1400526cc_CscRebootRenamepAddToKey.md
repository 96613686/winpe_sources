# CscRebootRenamepAddToKey

- ea: `0x1400526cc`
- end: `0x140052902`
- name: `CscRebootRenamepAddToKey`
- size: `566`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1400522a4`
- `0x1400525ac`

## callees

- `0x140018ee4`
- `0x1400218ac`
- `0x140021b04`
- `0x14002208c`
- `0x14002f010`
- `0x1400526cc`
- `0x140052d40`
- `0x140052db4`
- `0x140052e44`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400528d3`
- `ntoskrnl!ZwClose` at `0x1400528d3`

## pseudocode

```c
__int64 __fastcall CscRebootRenamepAddToKey(
        struct _UNICODE_STRING *a1,
        HANDLE *a2,
        unsigned int *a3,
        __int64 a4,
        __int64 a5,
        unsigned int *a6)
{
  HANDLE v7; // rcx
  unsigned int v8; // edi
  unsigned int v11; // ecx
  HANDLE v12; // rax
  int IndexString; // ebx
  int v14; // eax
  _BYTE v16[4]; // [rsp+30h] [rbp-A9h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-A5h]
  HANDLE Handle; // [rsp+38h] [rbp-A1h] BYREF
  struct _UNICODE_STRING v19; // [rsp+40h] [rbp-99h] BYREF
  struct _UNICODE_STRING v20; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-79h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+70h] [rbp-69h] BYREF
  char v23; // [rsp+80h] [rbp-59h] BYREF
  char v24; // [rsp+90h] [rbp-49h] BYREF
  char v25; // [rsp+A0h] [rbp-39h] BYREF

  ValueName.Buffer = L"LastIndexValue";
  v7 = 0;
  *(_QWORD *)&ValueName.Length = 1966108;
  v19.Buffer = (PWSTR)&v23;
  v8 = 0;
  *(_QWORD *)&v19.Length = 0x100000;
  v20.Buffer = (PWSTR)&v24;
  *(_QWORD *)&v20.Length = 0x100000;
  v21[1] = &v25;
  v21[0] = 3145728;
  Handle = 0;
  v17 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    if ( a3 )
      v11 = *a3;
    else
      LOBYTE(v11) = -1;
    if ( a2 )
      v12 = *a2;
    else
      LOBYTE(v12) = 0;
    WPP_SF_ZqD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)WPP_GLOBAL_Control, (_DWORD)a3, (_DWORD)a1, (char)v12, v11);
    v7 = Handle;
  }
  if ( a2 )
  {
    v7 = *a2;
    Handle = *a2;
  }
  if ( a3 )
  {
    v8 = *a3;
    v17 = *a3;
  }
  if ( !v7 )
  {
    v16[0] = 0;
    IndexString = CscRebootRenamepOpenKey(&Handle, a1, 1, v16);
    if ( IndexString < 0 )
      goto LABEL_29;
    if ( v16[0] )
    {
      v14 = CscRegistrypReadULong(Handle, &ValueName);
      v8 = v17;
      IndexString = v14;
      if ( v14 < 0 )
        goto LABEL_29;
    }
    else
    {
      v8 = 0;
    }
  }
  IndexString = CscRebootRenamepGetIndexString(v8, &v19);
  if ( IndexString >= 0 )
  {
    IndexString = CscRebootRenamepGetIndexString(v8 + 1, &v20);
    if ( IndexString >= 0 )
    {
      if ( !a6 || (IndexString = CscRebootRenamepGetStatusString(v8, v21), IndexString >= 0) )
      {
        IndexString = CscRegistrypWriteString(Handle, &v19);
        if ( IndexString >= 0 )
        {
          IndexString = CscRegistrypWriteString(Handle, &v20);
          if ( IndexString >= 0 )
          {
            if ( !a6 || (IndexString = CscRegistrypWriteULong(Handle, v21, *a6), IndexString >= 0) )
            {
              v8 += 2;
              IndexString = CscRegistrypWriteULong(Handle, &ValueName, v8);
            }
          }
        }
      }
    }
  }
LABEL_29:
  if ( a3 && IndexString >= 0 )
    *a3 = v8;
  if ( Handle )
  {
    if ( a2 )
      *a2 = Handle;
    else
      ZwClose(Handle);
  }
  return (unsigned int)IndexString;
}

```

## disassembly

```asm
0x1400526cc  push    rbp
0x1400526ce  push    rbx
0x1400526cf  push    rsi
0x1400526d0  push    rdi
0x1400526d1  push    r12
0x1400526d3  push    r13
0x1400526d5  push    r14
0x1400526d7  push    r15
0x1400526d9  lea     rbp, [rsp-0Fh]
0x1400526de  sub     rsp, 0E8h
0x1400526e5  mov     rax, cs:__security_cookie
0x1400526ec  xor     rax, rsp
0x1400526ef  mov     [rbp+47h+var_50], rax
0x1400526f3  mov     r13, [rbp+47h+arg_20]
0x1400526f7  lea     rax, aLastindexvalue; "LastIndexValue"
0x1400526fe  mov     r15, [rbp+47h+arg_28]
0x140052702  mov     rbx, rcx
0x140052705  mov     [rbp+47h+ValueName.Buffer], rax
0x140052709  xor     ecx, ecx
0x14005270b  lea     rax, [rbp+47h+var_A0]
0x14005270f  mov     qword ptr [rbp+47h+ValueName.Length], 1E001Ch
0x140052717  mov     [rsp+120h+var_E0.Buffer], rax
0x14005271c  xor     edi, edi
0x14005271e  lea     rax, [rbp+47h+var_90]
0x140052722  mov     qword ptr [rsp+120h+var_E0.Length], 100000h
0x14005272b  mov     [rsp+120h+var_D0.Buffer], rax
0x140052730  mov     r12, r9
0x140052733  lea     rax, [rbp+47h+var_80]
0x140052737  mov     qword ptr [rsp+120h+var_D0.Length], 100000h
0x140052740  mov     [rbp+47h+var_B8], rax
0x140052744  mov     rsi, r8
0x140052747  mov     r14, rdx
0x14005274a  mov     [rbp+47h+var_C0], 300000h
0x140052752  mov     [rsp+120h+Handle], rcx
0x140052757  mov     [rsp+120h+var_EC], edi
0x14005275b  mov     rdx, cs:WPP_GLOBAL_Control
0x140052762  lea     rax, WPP_GLOBAL_Control
0x140052769  cmp     rdx, rax
0x14005276c  jz      short loc_1400527A8
0x14005276e  mov     eax, [rdx+2Ch]
0x140052771  test    al, 40h
0x140052773  jz      short loc_1400527A8
0x140052775  test    r8, r8
0x140052778  jz      short loc_14005277F
0x14005277a  mov     ecx, [r8]
0x14005277d  jmp     short loc_140052782
0x14005277f  or      ecx, 0FFFFFFFFh
0x140052782  test    r14, r14
0x140052785  jz      short loc_14005278C
0x140052787  mov     rax, [r14]
0x14005278a  jmp     short loc_14005278E
0x14005278c  xor     eax, eax
0x14005278e  mov     [rsp+120h+var_F8], ecx
0x140052792  mov     r9, rbx
0x140052795  mov     rcx, [rdx+18h]
0x140052799  mov     [rsp+120h+var_100], rax
0x14005279e  call    WPP_SF_ZqD
0x1400527a3  mov     rcx, [rsp+120h+Handle]
0x1400527a8  test    r14, r14
0x1400527ab  jz      short loc_1400527B5
0x1400527ad  mov     rcx, [r14]
0x1400527b0  mov     [rsp+120h+Handle], rcx
0x1400527b5  test    rsi, rsi
0x1400527b8  jz      short loc_1400527C0
0x1400527ba  mov     edi, [rsi]
0x1400527bc  mov     [rsp+120h+var_EC], edi
0x1400527c0  test    rcx, rcx
0x1400527c3  jnz     short loc_140052813
0x1400527c5  mov     [rsp+120h+var_F0], cl
0x1400527c9  lea     r9, [rsp+120h+var_F0]
0x1400527ce  lea     rcx, [rsp+120h+Handle]; KeyHandle
0x1400527d3  mov     r8b, 1
0x1400527d6  mov     rdx, rbx
0x1400527d9  call    CscRebootRenamepOpenKey
0x1400527de  mov     ebx, eax
0x1400527e0  test    eax, eax
0x1400527e2  js      loc_1400528B4
0x1400527e8  cmp     [rsp+120h+var_F0], 0
0x1400527ed  jz      short loc_140052811
0x1400527ef  mov     rcx, [rsp+120h+Handle]; KeyHandle
0x1400527f4  lea     r8, [rsp+120h+var_EC]
0x1400527f9  lea     rdx, [rbp+47h+ValueName]; ValueName
0x1400527fd  call    CscRegistrypReadULong
0x140052802  mov     edi, [rsp+120h+var_EC]
0x140052806  mov     ebx, eax
0x140052808  test    eax, eax
0x14005280a  jns     short loc_140052813
0x14005280c  jmp     loc_1400528B4
0x140052811  xor     edi, edi
0x140052813  lea     rdx, [rsp+120h+var_E0]
0x140052818  mov     ecx, edi
0x14005281a  call    CscRebootRenamepGetIndexString
0x14005281f  mov     ebx, eax
0x140052821  test    eax, eax
0x140052823  js      loc_1400528B4
0x140052829  lea     ecx, [rdi+1]
0x14005282c  lea     rdx, [rsp+120h+var_D0]
0x140052831  call    CscRebootRenamepGetIndexString
0x140052836  mov     ebx, eax
0x140052838  test    eax, eax
0x14005283a  js      short loc_1400528B4
0x14005283c  test    r15, r15
0x14005283f  jz      short loc_140052852
0x140052841  lea     rdx, [rbp+47h+var_C0]
0x140052845  mov     ecx, edi
0x140052847  call    CscRebootRenamepGetStatusString
0x14005284c  mov     ebx, eax
0x14005284e  test    eax, eax
0x140052850  js      short loc_1400528B4
0x140052852  mov     rcx, [rsp+120h+Handle]; KeyHandle
0x140052857  lea     rdx, [rsp+120h+var_E0]; ValueName
0x14005285c  mov     r8, r12
0x14005285f  call    CscRegistrypWriteString
0x140052864  mov     ebx, eax
0x140052866  test    eax, eax
0x140052868  js      short loc_1400528B4
0x14005286a  mov     rcx, [rsp+120h+Handle]; KeyHandle
0x14005286f  lea     rdx, [rsp+120h+var_D0]; ValueName
0x140052874  mov     r8, r13
0x140052877  call    CscRegistrypWriteString
0x14005287c  mov     ebx, eax
0x14005287e  test    eax, eax
0x140052880  js      short loc_1400528B4
0x140052882  test    r15, r15
0x140052885  jz      short loc_14005289E
0x140052887  mov     r8d, [r15]
0x14005288a  lea     rdx, [rbp+47h+var_C0]
0x14005288e  mov     rcx, [rsp+120h+Handle]
0x140052893  call    CscRegistrypWriteULong
0x140052898  mov     ebx, eax
0x14005289a  test    eax, eax
0x14005289c  js      short loc_1400528B4
0x14005289e  mov     rcx, [rsp+120h+Handle]
0x1400528a3  lea     rdx, [rbp+47h+ValueName]
0x1400528a7  add     edi, 2
0x1400528aa  mov     r8d, edi
0x1400528ad  call    CscRegistrypWriteULong
0x1400528b2  mov     ebx, eax
0x1400528b4  test    rsi, rsi
0x1400528b7  jz      short loc_1400528BF
0x1400528b9  test    ebx, ebx
0x1400528bb  js      short loc_1400528BF
0x1400528bd  mov     [rsi], edi
0x1400528bf  mov     rcx, [rsp+120h+Handle]; Handle
0x1400528c4  test    rcx, rcx
0x1400528c7  jz      short loc_1400528DF
0x1400528c9  test    r14, r14
0x1400528cc  jz      short loc_1400528D3
0x1400528ce  mov     [r14], rcx
0x1400528d1  jmp     short loc_1400528DF
0x1400528d3  call    cs:__imp_ZwClose
0x1400528da  nop     dword ptr [rax+rax+00h]
0x1400528df  mov     eax, ebx
0x1400528e1  mov     rcx, [rbp+47h+var_50]
0x1400528e5  xor     rcx, rsp; StackCookie
0x1400528e8  call    __security_check_cookie
0x1400528ed  add     rsp, 0E8h
0x1400528f4  pop     r15
0x1400528f6  pop     r14
0x1400528f8  pop     r13
0x1400528fa  pop     r12
0x1400528fc  pop     rdi
0x1400528fd  pop     rsi
0x1400528fe  pop     rbx
0x1400528ff  pop     rbp
0x140052900  retn
```
