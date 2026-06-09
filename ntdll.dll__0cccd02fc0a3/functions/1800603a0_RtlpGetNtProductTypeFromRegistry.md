# RtlpGetNtProductTypeFromRegistry

- ea: `0x1800603a0`
- end: `0x180060573`
- name: `RtlpGetNtProductTypeFromRegistry`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002c60`

## callees

- `0x18005e7c0`
- `0x1800603a0`
- `0x18015e4b0`
- `0x18015e510`
- `0x18015e5b0`
- `0x180162000`

## string_xrefs

- `0x1800603c0`: `\Registry\Machine\System\CurrentControlSet\Control\ProductOptions`

## pseudocode

```c
__int64 __fastcall RtlpGetNtProductTypeFromRegistry(_DWORD *a1)
{
  int v2; // ebx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+44h] [rbp-BCh]
  int *v11; // [rsp+48h] [rbp-B8h]
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v14[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v17[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v18; // [rsp+C0h] [rbp-40h]
  _BYTE v19[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v20; // [rsp+D4h] [rbp-2Ch]
  unsigned int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+DCh] [rbp-24h] BYREF

  v17[0] = 48;
  v12[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ProductOptions";
  v17[3] = 576;
  v13[1] = L"ProductType";
  v12[0] = 8650882;
  v15[1] = L"LanmanNt";
  v7 = 0;
  v16[1] = L"ServerNt";
  v10 = 0;
  v14[1] = L"WinNt";
  v13[0] = 1572886;
  v17[2] = v12;
  v15[0] = 1179664;
  v16[0] = 1179664;
  v14[0] = 786442;
  Handle = 0;
  v17[1] = 0;
  v18 = 0;
  v2 = NtOpenKey(&Handle, 1, v17);
  if ( v2 >= 0 )
  {
    v2 = NtQueryValueKey(Handle, v13, 2, v19, 36, &v7);
    if ( v2 >= 0 )
    {
      if ( v20 != 1 || v21 < 2 )
      {
LABEL_12:
        v2 = -1073739509;
        goto LABEL_2;
      }
      v9[1] = v21;
      v11 = &v22;
      LOBYTE(v4) = 1;
      v9[0] = v21 - 2;
      if ( (unsigned __int8)RtlEqualUnicodeString(v9, v14, v4) )
      {
        *a1 = 1;
      }
      else
      {
        LOBYTE(v5) = 1;
        if ( !(unsigned __int8)RtlEqualUnicodeString(v9, v15, v5) )
        {
          LOBYTE(v6) = 1;
          if ( (unsigned __int8)RtlEqualUnicodeString(v9, v16, v6) )
          {
            *a1 = 3;
            goto LABEL_2;
          }
          goto LABEL_12;
        }
        *a1 = 2;
      }
    }
  }
LABEL_2:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800603a0  push    rbp
0x1800603a2  push    rbx
0x1800603a3  push    rdi
0x1800603a4  push    r15
0x1800603a6  lea     rbp, [rsp-8]
0x1800603ab  sub     rsp, 108h
0x1800603b2  mov     rax, cs:__security_cookie
0x1800603b9  xor     rax, rsp
0x1800603bc  mov     [rbp+20h+var_28], rax
0x1800603c0  lea     rax, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800603c7  mov     [rbp+20h+var_80], 30h ; '0'
0x1800603cf  mov     [rsp+120h+var_C8], rax
0x1800603d4  lea     r8, [rbp+20h+var_80]
0x1800603d8  lea     rax, aProducttype; "ProductType"
0x1800603df  mov     [rbp+20h+var_68], 240h
0x1800603e7  mov     [rsp+120h+var_B8], rax
0x1800603ec  mov     rdi, rcx
0x1800603ef  lea     rax, aLanmannt; "LanmanNt"
0x1800603f6  mov     [rsp+120h+var_D0], 840082h
0x1800603ff  mov     [rbp+20h+var_98], rax
0x180060403  lea     rcx, [rsp+120h+Handle]
0x180060408  lea     rax, aServernt; "ServerNt"
0x18006040f  mov     [rsp+120h+var_F0], 0
0x180060417  mov     [rbp+20h+var_88], rax
0x18006041b  xorps   xmm0, xmm0
0x18006041e  lea     rax, aWinnt; "WinNt"
0x180060425  mov     [rsp+120h+var_DC], 0
0x18006042d  mov     [rsp+120h+var_A8], rax
0x180060432  mov     edx, 1
0x180060437  lea     rax, [rsp+120h+var_D0]
0x18006043c  mov     [rsp+120h+var_C0], 180016h
0x180060445  mov     [rbp+20h+var_70], rax
0x180060449  mov     [rbp+20h+var_A0], 120010h
0x180060451  mov     [rbp+20h+var_90], 120010h
0x180060459  mov     [rsp+120h+var_B0], 0C000Ah
0x180060462  mov     [rsp+120h+Handle], 0
0x18006046b  mov     [rbp+20h+var_78], 0
0x180060473  movdqu  [rbp+20h+var_60], xmm0
0x180060478  call    NtOpenKey
0x18006047d  mov     ebx, eax
0x18006047f  test    eax, eax
0x180060481  jns     short loc_1800604AE
0x180060483  mov     rcx, [rsp+120h+Handle]; Handle
0x180060488  test    rcx, rcx
0x18006048b  jz      short loc_180060492
0x18006048d  call    NtClose
0x180060492  mov     eax, ebx
0x180060494  mov     rcx, [rbp+20h+var_28]
0x180060498  xor     rcx, rsp; StackCookie
0x18006049b  call    __security_check_cookie
0x1800604a0  add     rsp, 108h
0x1800604a7  pop     r15
0x1800604a9  pop     rdi
0x1800604aa  pop     rbx
0x1800604ab  pop     rbp
0x1800604ac  retn
0x1800604ae  mov     rcx, [rsp+120h+Handle]
0x1800604b3  lea     rax, [rsp+120h+var_F0]
0x1800604b8  mov     [rsp+120h+var_F8], rax
0x1800604bd  lea     r9, [rbp+20h+var_50]
0x1800604c1  mov     r15d, 2
0x1800604c7  mov     [rsp+120h+var_100], 24h ; '$'
0x1800604cf  mov     r8d, r15d
0x1800604d2  lea     rdx, [rsp+120h+var_C0]
0x1800604d7  call    NtQueryValueKey
0x1800604dc  mov     ebx, eax
0x1800604de  test    eax, eax
0x1800604e0  js      short loc_180060483
0x1800604e2  cmp     [rbp+20h+var_4C], 1
0x1800604e6  jnz     short loc_180060556
0x1800604e8  mov     rcx, [rbp+20h+var_48]
0x1800604ec  cmp     ecx, r15d
0x1800604ef  jb      short loc_180060556
0x1800604f1  lea     rax, [rbp+20h+var_48+4]
0x1800604f5  mov     [rsp+120h+var_DE], cx
0x1800604fa  mov     [rsp+120h+var_D8], rax
0x1800604ff  lea     rdx, [rsp+120h+var_B0]
0x180060504  movzx   eax, cx
0x180060507  mov     r8b, 1
0x18006050a  sub     ax, r15w
0x18006050e  lea     rcx, [rsp+120h+var_E0]
0x180060513  mov     [rsp+120h+var_E0], ax
0x180060518  call    RtlEqualUnicodeString
0x18006051d  test    al, al
0x18006051f  jnz     short loc_180060560
0x180060521  mov     r8b, 1
0x180060524  lea     rdx, [rbp+20h+var_A0]
0x180060528  lea     rcx, [rsp+120h+var_E0]
0x18006052d  call    RtlEqualUnicodeString
0x180060532  test    al, al
0x180060534  jnz     short loc_18006056B
0x180060536  mov     r8b, 1
0x180060539  lea     rdx, [rbp+20h+var_90]
0x18006053d  lea     rcx, [rsp+120h+var_E0]
0x180060542  call    RtlEqualUnicodeString
0x180060547  test    al, al
0x180060549  jz      short loc_180060556
0x18006054b  mov     dword ptr [rdi], 3
0x180060551  jmp     loc_180060483
0x180060556  mov     ebx, 0C000090Bh
0x18006055b  jmp     loc_180060483
0x180060560  mov     dword ptr [rdi], 1
0x180060566  jmp     loc_180060483
0x18006056b  mov     [rdi], r15d
0x18006056e  jmp     loc_180060483
```
