# Wow64NtCreateKey

- ea: `0x1800602e0`
- end: `0x1800606f2`
- name: `Wow64NtCreateKey`
- size: `1042`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005cc70`
- `0x180061a20`
- `0x1800d1400`
- `0x1800d1550`
- `0x18018f578`

## callees

- `0x18005fa00`
- `0x1800602e0`

## import_xrefs

- `ntdll!NtCreateKeyTransacted` at `0x1800605b2`
- `ntdll!NtCreateKeyTransacted` at `0x1800605ef`
- `ntdll!NtCreateKeyTransacted` at `0x180060667`
- `ntdll!NtCreateKeyTransacted` at `0x1800605b2`
- `ntdll!NtCreateKeyTransacted` at `0x1800605ef`
- `ntdll!NtCreateKeyTransacted` at `0x180060667`
- `ntdll!NtCreateKey` at `0x1800603c2`
- `ntdll!NtCreateKey` at `0x1800604ee`
- `ntdll!NtCreateKey` at `0x180060634`
- `ntdll!NtCreateKey` at `0x1800603c2`
- `ntdll!NtCreateKey` at `0x1800604ee`
- `ntdll!NtCreateKey` at `0x180060634`
- `ntdll!NtClose` at `0x18006058c`
- `ntdll!NtClose` at `0x1800605c3`
- `ntdll!NtClose` at `0x180060675`
- `ntdll!NtClose` at `0x18006058c`
- `ntdll!NtClose` at `0x1800605c3`
- `ntdll!NtClose` at `0x180060675`
- `ntdll!RtlFreeHeap` at `0x180060407`
- `ntdll!RtlFreeHeap` at `0x180060407`
- `ntdll!NtOpenKeyEx` at `0x1800606a1`
- `ntdll!NtOpenKeyEx` at `0x1800606a1`
- `ntdll!NtSetInformationKey` at `0x180060572`
- `ntdll!NtSetInformationKey` at `0x180060572`
- `ntdll!NtOpenKeyTransactedEx` at `0x1800606e4`
- `ntdll!NtOpenKeyTransactedEx` at `0x1800606e4`

## pseudocode

```c
__int64 __fastcall Wow64NtCreateKey(
        HANDLE *a1,
        ACCESS_MASK a2,
        __int128 *a3,
        int a4,
        PUNICODE_STRING Class,
        ULONG CreateOptions,
        __int64 a7,
        PULONG Disposition)
{
  __int128 v8; // xmm0
  HANDLE *v9; // r13
  __int128 v10; // xmm1
  __int128 v12; // xmm0
  __int64 result; // rax
  ULONG v14; // esi
  __int64 v15; // rdi
  ULONG *v16; // r14
  struct _UNICODE_STRING *v17; // r15
  NTSTATUS v18; // eax
  int v19; // ebx
  __int16 v20; // r8
  PUNICODE_STRING ObjectName; // rax
  USHORT Length; // r13
  __int16 v23; // dx
  WCHAR *v24; // rcx
  NTSTATUS v25; // eax
  WCHAR *v26; // rax
  __int16 v27; // ax
  NTSTATUS v28; // edi
  USHORT v29; // r13
  int v30; // eax
  int v31; // eax
  int KeySetInformation; // [rsp+40h] [rbp-59h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-51h] BYREF
  WCHAR *v34; // [rsp+50h] [rbp-49h]
  PVOID P; // [rsp+58h] [rbp-41h] BYREF
  __int64 v36; // [rsp+60h] [rbp-39h] BYREF
  __int16 v37; // [rsp+68h] [rbp-31h]
  char v38; // [rsp+6Ah] [rbp-2Fh]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-29h] BYREF
  __int16 v41; // [rsp+F0h] [rbp+57h]
  int v42; // [rsp+F8h] [rbp+5Fh] BYREF

  v42 = a4;
  v8 = *a3;
  v9 = a1;
  v10 = a3[1];
  v36 = 0;
  v37 = 0;
  v38 = 0;
  LOBYTE(v42) = 0;
  *(_OWORD *)&ObjectAttributes.Length = v8;
  P = 0;
  v12 = a3[2];
  KeySetInformation = 0;
  KeyHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v12;
  *(_OWORD *)&ObjectAttributes.ObjectName = v10;
  result = ConstructKernelKeyPath(
             a2,
             (unsigned int)&ObjectAttributes,
             (unsigned int)&KeySetInformation,
             (unsigned int)&v36,
             (__int64)&v42,
             (__int64)&P);
  if ( (int)result < 0 )
    return result;
  v14 = CreateOptions;
  v15 = a7;
  v16 = Disposition;
  v17 = Class;
  if ( a7 )
    v18 = NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, Class, CreateOptions, a7, Disposition);
  else
    v18 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, Class, CreateOptions, Disposition);
  v19 = v18;
  if ( v18 == -1073741772 )
  {
    if ( (_BYTE)v36 )
    {
      v20 = WORD2(v36);
      if ( WORD2(v36) )
      {
        ObjectName = ObjectAttributes.ObjectName;
        Length = ObjectAttributes.ObjectName->Length;
        if ( WORD1(v36) )
        {
          ObjectAttributes.ObjectName->Length = WORD1(v36);
          if ( v15 )
            v31 = NtOpenKeyTransactedEx(&KeyHandle, a2, &ObjectAttributes, v14, v15);
          else
            v31 = NtOpenKeyEx(&KeyHandle, a2, &ObjectAttributes, v14);
          v19 = v31;
          if ( v31 < 0 )
          {
LABEL_41:
            v9 = a1;
            goto LABEL_5;
          }
          Length -= WORD1(v36);
          v20 = WORD2(v36);
          ObjectAttributes.ObjectName->Buffer += (unsigned __int64)WORD1(v36) >> 1;
          ObjectAttributes.RootDirectory = KeyHandle;
          ObjectName = ObjectAttributes.ObjectName;
        }
        else
        {
          v19 = 0;
        }
        v23 = v20 - 2;
        v24 = ObjectName->Buffer + 1;
        ObjectName->Buffer = v24;
        ObjectAttributes.ObjectName->MaximumLength -= 2;
        while ( 1 )
        {
          v34 = v24;
          if ( !v23 )
            break;
          do
          {
            if ( *v24 == 92 )
              break;
            ++v24;
            v23 -= 2;
          }
          while ( v23 );
          v34 = v24;
          v41 = v23;
          ObjectAttributes.ObjectName->Length = 2
                                              * ((__int64)(unsigned int)((_DWORD)v24
                                                                       - LODWORD(ObjectAttributes.ObjectName->Buffer)) >> 1);
          if ( v15 )
            v25 = NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v15, v16);
          else
            v25 = NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v16);
          v19 = v25;
          if ( ObjectAttributes.RootDirectory )
          {
            NtClose(ObjectAttributes.RootDirectory);
            ObjectAttributes.RootDirectory = 0;
          }
          if ( v19 < 0 )
            goto LABEL_41;
          v26 = v34 + 1;
          if ( !v41 )
            v26 = v34;
          v24 = v26;
          ObjectAttributes.ObjectName->Buffer = v26;
          ObjectAttributes.RootDirectory = KeyHandle;
          v27 = v41 - 2;
          if ( !v41 )
            v27 = 0;
          v23 = v27;
        }
        if ( v19 >= 0 )
        {
          v29 = Length - WORD2(v36);
          if ( v29 )
          {
            ObjectAttributes.ObjectName->Length = v29;
            v30 = v15
                ? NtCreateKeyTransacted(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v15, v16)
                : NtCreateKey(&KeyHandle, a2, &ObjectAttributes, 0, v17, v14, v16);
            v19 = v30;
            if ( ObjectAttributes.RootDirectory )
            {
              NtClose(ObjectAttributes.RootDirectory);
              ObjectAttributes.RootDirectory = 0;
            }
          }
        }
        goto LABEL_41;
      }
    }
  }
LABEL_5:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v19 >= 0 )
  {
    if ( (_BYTE)v42 )
    {
      if ( KeySetInformation )
      {
        KeySetInformation &= 0xF01u;
        v28 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
        if ( v28 < 0 )
        {
          NtClose(KeyHandle);
          return (unsigned int)v28;
        }
      }
    }
    *v9 = KeyHandle;
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800602e0  mov     [rsp-8+arg_18], r9d
0x1800602e5  mov     [rsp-8+arg_0], rcx
0x1800602ea  push    rbp
0x1800602eb  push    r12
0x1800602ed  push    r13
0x1800602ef  lea     rbp, [rsp-27h]
0x1800602f4  sub     rsp, 0C0h
0x1800602fb  movups  xmm0, xmmword ptr [r8]
0x1800602ff  xor     eax, eax
0x180060301  mov     r13, rcx
0x180060304  movups  xmm1, xmmword ptr [r8+10h]
0x180060309  xor     ecx, ecx
0x18006030b  mov     [rbp+37h+var_70], rax
0x18006030f  mov     [rbp+37h+var_68], ax
0x180060313  lea     r9, [rbp+37h+var_70]
0x180060317  mov     [rbp+37h+var_66], al
0x18006031a  mov     r12d, edx
0x18006031d  mov     byte ptr [rbp+37h+arg_18], al
0x180060320  lea     rdx, [rbp+37h+ObjectAttributes]
0x180060324  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x180060328  lea     rax, [rbp+37h+P]
0x18006032c  mov     [rbp+37h+P], rcx
0x180060330  movups  xmm0, xmmword ptr [r8+20h]
0x180060335  mov     qword ptr [rsp+0D0h+CreateOptions], rax
0x18006033a  lea     r8, [rbp+37h+KeySetInformation]
0x18006033e  mov     [rbp+37h+KeySetInformation], ecx
0x180060341  lea     rax, [rbp+37h+arg_18]
0x180060345  mov     [rbp+37h+KeyHandle], rcx
0x180060349  mov     ecx, r12d
0x18006034c  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060350  mov     [rsp+0D0h+Class], rax
0x180060355  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm1
0x180060359  call    ConstructKernelKeyPath
0x18006035e  test    eax, eax
0x180060360  js      loc_18006043B
0x180060366  mov     [rsp+0D0h+arg_8], rbx
0x18006036e  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180060372  mov     [rsp+0D0h+var_18], rsi
0x18006037a  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18006037e  mov     esi, [rbp+37h+arg_28]
0x180060381  xor     r9d, r9d; TitleIndex
0x180060384  mov     [rsp+0D0h+var_20], rdi
0x18006038c  mov     edx, r12d; DesiredAccess
0x18006038f  mov     rdi, [rbp+37h+arg_30]
0x180060393  mov     [rsp+0D0h+var_28], r14
0x18006039b  mov     r14, [rbp+37h+arg_38]
0x18006039f  mov     [rsp+0D0h+var_30], r15
0x1800603a7  mov     r15, [rbp+37h+arg_20]
0x1800603ab  test    rdi, rdi
0x1800603ae  jnz     loc_18006059F
0x1800603b4  mov     [rsp+0D0h+Disposition], r14; Disposition
0x1800603b9  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x1800603bd  mov     [rsp+0D0h+Class], r15; Class
0x1800603c2  call    cs:__imp_NtCreateKey
0x1800603c9  nop     dword ptr [rax+rax+00h]
0x1800603ce  mov     ebx, eax
0x1800603d0  cmp     eax, 0C0000034h
0x1800603d5  jz      short loc_180060449
0x1800603d7  mov     r8, [rbp+37h+P]; P
0x1800603db  mov     r15, [rsp+0D0h+var_30]
0x1800603e3  mov     r14, [rsp+0D0h+var_28]
0x1800603eb  mov     rsi, [rsp+0D0h+var_18]
0x1800603f3  test    r8, r8
0x1800603f6  jz      short loc_180060413
0x1800603f8  mov     rcx, gs:60h
0x180060401  xor     edx, edx; Flags
0x180060403  mov     rcx, [rcx+30h]; HeapHandle
0x180060407  call    cs:__imp_RtlFreeHeap
0x18006040e  nop     dword ptr [rax+rax+00h]
0x180060413  test    ebx, ebx
0x180060415  js      short loc_180060429
0x180060417  cmp     byte ptr [rbp+37h+arg_18], 0
0x18006041b  jnz     loc_18006054C
0x180060421  mov     rax, [rbp+37h+KeyHandle]
0x180060425  mov     [r13+0], rax
0x180060429  mov     eax, ebx
0x18006042b  mov     rbx, [rsp+0D0h+arg_8]
0x180060433  mov     rdi, [rsp+0D0h+var_20]
0x18006043b  add     rsp, 0C0h
0x180060442  pop     r13
0x180060444  pop     r12
0x180060446  pop     rbp
0x180060447  retn
0x180060449  cmp     byte ptr [rbp+37h+var_70], 0
0x18006044d  jz      short loc_1800603D7
0x18006044f  movzx   r8d, word ptr [rbp+37h+var_70+4]
0x180060454  test    r8w, r8w
0x180060458  jz      loc_1800603D7
0x18006045e  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x180060462  movzx   ecx, word ptr [rbp+37h+var_70+2]
0x180060466  movzx   r13d, word ptr [rax]
0x18006046a  test    cx, cx
0x18006046d  jnz     loc_18006068B
0x180060473  xor     ebx, ebx
0x180060475  mov     rcx, [rax+8]
0x180060479  lea     edx, [r8-2]
0x18006047d  add     rcx, 2
0x180060481  mov     r8d, 0FFFEh
0x180060487  mov     [rax+8], rcx
0x18006048b  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18006048f  add     [rax+2], r8w
0x180060494  mov     [rbp+37h+var_80], rcx
0x180060498  test    dx, dx
0x18006049b  jz      loc_180060600
0x1800604a1  cmp     word ptr [rcx], 5Ch ; '\'
0x1800604a5  jz      short loc_1800604B1
0x1800604a7  add     rcx, 2
0x1800604ab  add     dx, r8w
0x1800604af  jnz     short loc_1800604A1
0x1800604b1  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x1800604b5  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800604b9  mov     [rbp+37h+var_80], rcx
0x1800604bd  xor     r9d, r9d; TitleIndex
0x1800604c0  mov     [rbp+37h+arg_10], dx
0x1800604c4  mov     edx, r12d; DesiredAccess
0x1800604c7  sub     ecx, [rax+8]
0x1800604ca  sar     rcx, 1
0x1800604cd  add     cx, cx
0x1800604d0  mov     [rax], cx
0x1800604d3  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x1800604d7  test    rdi, rdi
0x1800604da  jnz     loc_1800605DC
0x1800604e0  mov     [rsp+0D0h+Disposition], r14; Disposition
0x1800604e5  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x1800604e9  mov     [rsp+0D0h+Class], r15; Class
0x1800604ee  call    cs:__imp_NtCreateKey
0x1800604f5  nop     dword ptr [rax+rax+00h]
0x1800604fa  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x1800604fe  mov     ebx, eax
0x180060500  test    rcx, rcx
0x180060503  jnz     loc_1800605C3
0x180060509  test    ebx, ebx
0x18006050b  js      loc_18006064B
0x180060511  movzx   edx, [rbp+37h+arg_10]
0x180060515  mov     r8d, 0FFFEh
0x18006051b  mov     rcx, [rbp+37h+var_80]
0x18006051f  test    dx, dx
0x180060522  lea     rax, [rcx+2]
0x180060526  cmovz   rax, rcx
0x18006052a  mov     rcx, rax
0x18006052d  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x180060531  mov     [rax+8], rcx
0x180060535  mov     rax, [rbp+37h+KeyHandle]
0x180060539  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x18006053d  lea     eax, [rdx-2]
0x180060540  cmovz   ax, dx
0x180060544  movzx   edx, ax
0x180060547  jmp     loc_180060494
0x18006054c  mov     eax, [rbp+37h+KeySetInformation]
0x18006054f  test    eax, eax
0x180060551  jz      loc_180060421
0x180060557  mov     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18006055b  lea     r8, [rbp+37h+KeySetInformation]; KeySetInformation
0x18006055f  and     eax, 0F01h
0x180060564  mov     r9d, 4; KeySetInformationLength
0x18006056a  mov     edx, 5; KeySetInformationClass
0x18006056f  mov     [rbp+37h+KeySetInformation], eax
0x180060572  call    cs:__imp_NtSetInformationKey
0x180060579  nop     dword ptr [rax+rax+00h]
0x18006057e  mov     edi, eax
0x180060580  test    eax, eax
0x180060582  jns     loc_180060421
0x180060588  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18006058c  call    cs:__imp_NtClose
0x180060593  nop     dword ptr [rax+rax+00h]
0x180060598  mov     eax, edi
0x18006059a  jmp     loc_18006042B
0x18006059f  mov     [rsp+0D0h+var_98], r14
0x1800605a4  mov     [rsp+0D0h+Disposition], rdi
0x1800605a9  mov     [rsp+0D0h+CreateOptions], esi
0x1800605ad  mov     [rsp+0D0h+Class], r15
0x1800605b2  call    cs:__imp_NtCreateKeyTransacted
0x1800605b9  nop     dword ptr [rax+rax+00h]
0x1800605be  jmp     loc_1800603CE
0x1800605c3  call    cs:__imp_NtClose
0x1800605ca  nop     dword ptr [rax+rax+00h]
0x1800605cf  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x1800605d7  jmp     loc_180060509
0x1800605dc  mov     [rsp+0D0h+var_98], r14
0x1800605e1  mov     [rsp+0D0h+Disposition], rdi
0x1800605e6  mov     [rsp+0D0h+CreateOptions], esi
0x1800605ea  mov     [rsp+0D0h+Class], r15
0x1800605ef  call    cs:__imp_NtCreateKeyTransacted
0x1800605f6  nop     dword ptr [rax+rax+00h]
0x1800605fb  jmp     loc_1800604FA
0x180060600  test    ebx, ebx
0x180060602  js      short loc_18006064B
0x180060604  sub     r13w, word ptr [rbp+37h+var_70+4]
0x180060609  jz      short loc_18006064B
0x18006060b  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x18006060f  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x180060613  xor     r9d, r9d; TitleIndex
0x180060616  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18006061a  mov     edx, r12d; DesiredAccess
0x18006061d  mov     [rax], r13w
0x180060621  test    rdi, rdi
0x180060624  jnz     short loc_180060654
0x180060626  mov     [rsp+0D0h+Disposition], r14; Disposition
0x18006062b  mov     [rsp+0D0h+CreateOptions], esi; CreateOptions
0x18006062f  mov     [rsp+0D0h+Class], r15; Class
0x180060634  call    cs:__imp_NtCreateKey
0x18006063b  nop     dword ptr [rax+rax+00h]
0x180060640  mov     rcx, [rbp+37h+ObjectAttributes.RootDirectory]; Handle
0x180060644  mov     ebx, eax
0x180060646  test    rcx, rcx
0x180060649  jnz     short loc_180060675
0x18006064b  mov     r13, [rbp+37h+arg_0]
0x18006064f  jmp     loc_1800603D7
0x180060654  mov     [rsp+0D0h+var_98], r14
0x180060659  mov     [rsp+0D0h+Disposition], rdi
0x18006065e  mov     [rsp+0D0h+CreateOptions], esi
0x180060662  mov     [rsp+0D0h+Class], r15
0x180060667  call    cs:__imp_NtCreateKeyTransacted
0x18006066e  nop     dword ptr [rax+rax+00h]
0x180060673  jmp     short loc_180060640
0x180060675  call    cs:__imp_NtClose
0x18006067c  nop     dword ptr [rax+rax+00h]
0x180060681  mov     [rbp+37h+ObjectAttributes.RootDirectory], 0
0x180060689  jmp     short loc_18006064B
0x18006068b  mov     [rax], cx
0x18006068e  lea     rcx, [rbp+37h+KeyHandle]
0x180060692  lea     r8, [rbp+37h+ObjectAttributes]
0x180060696  mov     r9d, esi
0x180060699  mov     edx, r12d
0x18006069c  test    rdi, rdi
0x18006069f  jnz     short loc_1800606DF
0x1800606a1  call    cs:__imp_NtOpenKeyEx
0x1800606a8  nop     dword ptr [rax+rax+00h]
0x1800606ad  mov     ebx, eax
0x1800606af  test    eax, eax
0x1800606b1  js      short loc_18006064B
0x1800606b3  movzx   eax, word ptr [rbp+37h+var_70+2]
0x1800606b7  mov     rcx, [rbp+37h+ObjectAttributes.ObjectName]
0x1800606bb  sub     r13w, ax
0x1800606bf  movzx   r8d, word ptr [rbp+37h+var_70+4]
0x1800606c4  shr     rax, 1
0x1800606c7  add     rax, rax
0x1800606ca  add     [rcx+8], rax
0x1800606ce  mov     rax, [rbp+37h+KeyHandle]
0x1800606d2  mov     [rbp+37h+ObjectAttributes.RootDirectory], rax
0x1800606d6  mov     rax, [rbp+37h+ObjectAttributes.ObjectName]
0x1800606da  jmp     loc_180060475
0x1800606df  mov     [rsp+0D0h+Class], rdi
0x1800606e4  call    cs:__imp_NtOpenKeyTransactedEx
0x1800606eb  nop     dword ptr [rax+rax+00h]
0x1800606f0  jmp     short loc_1800606AD
```
