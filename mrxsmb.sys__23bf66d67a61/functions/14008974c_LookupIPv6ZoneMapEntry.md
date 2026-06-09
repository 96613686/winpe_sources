# LookupIPv6ZoneMapEntry

- ea: `0x14008974c`
- end: `0x14008992b`
- name: `LookupIPv6ZoneMapEntry`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140089934`

## callees

- `0x140039fa8`
- `0x140059f00`
- `0x14008974c`
- `0x14008a78c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400898ae`
- `ntoskrnl!ZwOpenKey` at `0x1400898ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008986f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008986f`
- `ntoskrnl!ExAllocatePool2` at `0x1400897de`
- `ntoskrnl!ExAllocatePool2` at `0x1400897de`
- `ntoskrnl!ZwClose` at `0x140089904`
- `ntoskrnl!ZwClose` at `0x140089904`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400898ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400898ef`

## pseudocode

```c
__int64 __fastcall LookupIPv6ZoneMapEntry(unsigned __int16 *a1, const WCHAR *a2, int *a3)
{
  _WORD *v4; // rcx
  void *v7; // rbx
  unsigned int v8; // r14d
  _WORD *Pool2; // rax
  unsigned int v10; // edi
  __int128 v12; // [rsp+20h] [rbp-50h] BYREF
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+B0h] [rbp+40h] BYREF
  void *KeyHandle; // [rsp+C0h] [rbp+50h] BYREF

  KeyHandle = 0;
  v4 = (_WORD *)*((_QWORD *)a1 + 1);
  v15 = 3;
  *a3 = 3;
  v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( *v4 == 91 && v4[((unsigned __int64)*a1 >> 1) - 1] == 93 )
  {
    v7 = 0;
    v12 = *(_OWORD *)a1;
LABEL_10:
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 || (int)RegQueryZoneFromKey(KeyHandle, &v12, &v15) < 0 )
    {
      v10 = -1073741772;
    }
    else
    {
      v10 = 0;
      *a3 = v15;
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0x7A4D6D53u);
    goto LABEL_16;
  }
  v8 = *a1 + 4;
  Pool2 = (_WORD *)ExAllocatePool2(258, v8, 2051894611);
  v7 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = 91;
    memmove(Pool2 + 1, *((const void **)a1 + 1), *a1);
    *((_WORD *)v7 + ((unsigned __int64)v8 >> 1) - 1) = 93;
    *((_QWORD *)&v12 + 1) = v7;
    LOWORD(v12) = v8;
    WORD1(v12) = v8;
    goto LABEL_10;
  }
  v10 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids);
  }
LABEL_16:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v10;
}

```

## disassembly

```asm
0x14008974c  mov     [rsp-38h+arg_8], rbx
0x140089751  push    rbp
0x140089752  push    rsi
0x140089753  push    rdi
0x140089754  push    r12
0x140089756  push    r13
0x140089758  push    r14
0x14008975a  push    r15
0x14008975c  mov     rbp, rsp
0x14008975f  sub     rsp, 70h
0x140089763  xorps   xmm0, xmm0
0x140089766  mov     [rbp+KeyHandle], 0
0x14008976e  mov     eax, 3
0x140089773  mov     rdi, rcx
0x140089776  mov     rcx, [rcx+8]
0x14008977a  mov     r15, r8
0x14008977d  mov     [rbp+arg_0], eax
0x140089780  mov     r12, rdx
0x140089783  mov     [r8], eax
0x140089786  mov     eax, 5Bh ; '['
0x14008978b  movups  [rbp+var_50], xmm0
0x14008978f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140089793  lea     r13d, [rax+2]
0x140089797  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008979b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008979f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400897a3  cmp     [rcx], ax
0x1400897a6  jnz     short loc_1400897C5
0x1400897a8  movzx   eax, word ptr [rdi]
0x1400897ab  shr     rax, 1
0x1400897ae  cmp     [rcx+rax*2-2], r13w
0x1400897b4  jnz     short loc_1400897C5
0x1400897b6  movups  xmm0, xmmword ptr [rdi]
0x1400897b9  xor     ebx, ebx
0x1400897bb  movdqu  [rbp+var_50], xmm0
0x1400897c0  jmp     loc_140089868
0x1400897c5  movzx   r14d, word ptr [rdi]
0x1400897c9  mov     r8d, 7A4D6D53h
0x1400897cf  add     r14d, 4
0x1400897d3  mov     ecx, 102h
0x1400897d8  mov     edx, r14d
0x1400897db  mov     esi, r14d
0x1400897de  call    cs:__imp_ExAllocatePool2
0x1400897e5  nop     dword ptr [rax+rax+00h]
0x1400897ea  mov     rbx, rax
0x1400897ed  test    rax, rax
0x1400897f0  jnz     short loc_14008983B
0x1400897f2  mov     edi, 0C000009Ah
0x1400897f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400897fe  lea     rax, WPP_GLOBAL_Control
0x140089805  cmp     rcx, rax
0x140089808  jz      loc_1400898FB
0x14008980e  mov     eax, [rcx+2Ch]
0x140089811  test    al, 1
0x140089813  jz      loc_1400898FB
0x140089819  cmp     byte ptr [rcx+29h], 1
0x14008981d  jb      loc_1400898FB
0x140089823  mov     rcx, [rcx+18h]
0x140089827  lea     edx, [rbx+45h]
0x14008982a  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x140089831  call    WPP_SF_
0x140089836  jmp     loc_1400898FB
0x14008983b  mov     word ptr [rax], 5Bh ; '['
0x140089840  lea     rcx, [rax+2]; void *
0x140089844  movzx   r8d, word ptr [rdi]; Size
0x140089848  mov     rdx, [rdi+8]; Src
0x14008984c  call    memmove
0x140089851  shr     rsi, 1
0x140089854  mov     [rbx+rsi*2-2], r13w
0x14008985a  mov     qword ptr [rbp+var_50+8], rbx
0x14008985e  mov     word ptr [rbp+var_50], r14w
0x140089863  mov     word ptr [rbp+var_50+2], r14w
0x140089868  mov     rdx, r12; SourceString
0x14008986b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14008986f  call    cs:__imp_RtlInitUnicodeString
0x140089876  nop     dword ptr [rax+rax+00h]
0x14008987b  lea     rax, [rbp+DestinationString]
0x14008987f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140089886  xorps   xmm0, xmm0
0x140089889  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14008988d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140089891  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140089899  mov     edx, 20019h; DesiredAccess
0x14008989e  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400898a5  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400898a9  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400898ae  call    cs:__imp_ZwOpenKey
0x1400898b5  nop     dword ptr [rax+rax+00h]
0x1400898ba  test    eax, eax
0x1400898bc  js      short loc_1400898DD
0x1400898be  mov     rcx, [rbp+KeyHandle]
0x1400898c2  lea     r8, [rbp+arg_0]
0x1400898c6  lea     rdx, [rbp+var_50]
0x1400898ca  call    RegQueryZoneFromKey
0x1400898cf  test    eax, eax
0x1400898d1  js      short loc_1400898DD
0x1400898d3  xor     edi, edi
0x1400898d5  mov     eax, [rbp+arg_0]
0x1400898d8  mov     [r15], eax
0x1400898db  jmp     short loc_1400898E2
0x1400898dd  mov     edi, 0C0000034h
0x1400898e2  test    rbx, rbx
0x1400898e5  jz      short loc_1400898FB
0x1400898e7  mov     edx, 7A4D6D53h; Tag
0x1400898ec  mov     rcx, rbx; P
0x1400898ef  call    cs:__imp_ExFreePoolWithTag
0x1400898f6  nop     dword ptr [rax+rax+00h]
0x1400898fb  mov     rcx, [rbp+KeyHandle]; Handle
0x1400898ff  test    rcx, rcx
0x140089902  jz      short loc_140089910
0x140089904  call    cs:__imp_ZwClose
0x14008990b  nop     dword ptr [rax+rax+00h]
0x140089910  mov     rbx, [rsp+70h+arg_8]
0x140089918  mov     eax, edi
0x14008991a  add     rsp, 70h
0x14008991e  pop     r15
0x140089920  pop     r14
0x140089922  pop     r13
0x140089924  pop     r12
0x140089926  pop     rdi
0x140089927  pop     rsi
0x140089928  pop     rbp
0x140089929  retn
```
