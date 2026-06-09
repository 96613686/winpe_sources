# ClassPnpLogDeviceDescriptor

- ea: `0x14003dbfc`
- end: `0x14003df01`
- name: `ClassPnpLogDeviceDescriptor`
- size: `773`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400579b4`

## callees

- `0x140001008`
- `0x1400010f8`
- `0x140020180`
- `0x14003dbfc`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14003dea6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003deb7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003dec8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003ded9`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003dea6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003deb7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003dec8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003ded9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc76`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dca3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcfd`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dc76`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dca3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcd0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003dcfd`

## pseudocode

```c
void __fastcall ClassPnpLogDeviceDescriptor(__int64 a1)
{
  _QWORD *v1; // rdi
  unsigned int *v2; // rbx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // rcx
  char v14; // [rsp+30h] [rbp-D0h] BYREF
  char v15; // [rsp+31h] [rbp-CFh] BYREF
  char v16; // [rsp+32h] [rbp-CEh] BYREF
  char v17; // [rsp+33h] [rbp-CDh] BYREF
  unsigned int v18; // [rsp+34h] [rbp-CCh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v21; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24[9]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v25[2]; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD *v26; // [rsp+D0h] [rbp-30h]
  __int64 v27; // [rsp+D8h] [rbp-28h]
  wchar_t *Buffer; // [rsp+E0h] [rbp-20h]
  _DWORD v29[2]; // [rsp+E8h] [rbp-18h] BYREF
  _DWORD *v30; // [rsp+F0h] [rbp-10h]
  __int64 v31; // [rsp+F8h] [rbp-8h]
  wchar_t *v32; // [rsp+100h] [rbp+0h]
  _DWORD v33[2]; // [rsp+108h] [rbp+8h] BYREF
  _DWORD *v34; // [rsp+110h] [rbp+10h]
  __int64 v35; // [rsp+118h] [rbp+18h]
  wchar_t *v36; // [rsp+120h] [rbp+20h]
  _DWORD v37[2]; // [rsp+128h] [rbp+28h] BYREF
  unsigned int *v38; // [rsp+130h] [rbp+30h]
  __int64 v39; // [rsp+138h] [rbp+38h]
  __int64 *v40; // [rsp+140h] [rbp+40h]
  __int64 v41; // [rsp+148h] [rbp+48h]
  char *v42; // [rsp+150h] [rbp+50h]
  __int64 v43; // [rsp+158h] [rbp+58h]
  char *v44; // [rsp+160h] [rbp+60h]
  __int64 v45; // [rsp+168h] [rbp+68h]
  char *v46; // [rsp+170h] [rbp+70h]
  __int64 v47; // [rsp+178h] [rbp+78h]
  char *v48; // [rsp+180h] [rbp+80h]
  __int64 v49; // [rsp+188h] [rbp+88h]

  v1 = *(_QWORD **)(a1 + 64);
  v2 = (unsigned int *)v1[65];
  DestinationString = 0;
  UnicodeString = 0;
  v21 = 0;
  v22 = 0;
  if ( v1[65] )
  {
    v3 = v2[3];
    if ( (_DWORD)v3 )
      ClasspGetUnicodeStringFromAnsiAtOffset(v2, v3, v2[1], &DestinationString);
    else
      RtlInitUnicodeString(&DestinationString, 0);
    v4 = v2[4];
    if ( (_DWORD)v4 )
      ClasspGetUnicodeStringFromAnsiAtOffset(v2, v4, v2[1], &UnicodeString);
    else
      RtlInitUnicodeString(&UnicodeString, 0);
    v5 = v2[5];
    if ( (_DWORD)v5 )
      ClasspGetUnicodeStringFromAnsiAtOffset(v2, v5, v2[1], &v21);
    else
      RtlInitUnicodeString(&v21, 0);
    v6 = v2[6];
    if ( (_DWORD)v6 )
      ClasspGetUnicodeStringFromAnsiAtOffset(v2, v6, v2[1], &v22);
    else
      RtlInitUnicodeString(&v22, 0);
    if ( (unsigned int)dword_14004D060 > 5 && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v8) )
    {
      v10 = v1[146] + 4LL;
      v24[5] = 16;
      v24[4] = v10;
      v24[6] = (__int64)v25;
      v24[8] = (__int64)v22.Buffer;
      v25[0] = v22.Length;
      v26 = v29;
      Buffer = UnicodeString.Buffer;
      v29[0] = UnicodeString.Length;
      v30 = v33;
      v32 = DestinationString.Buffer;
      v33[0] = DestinationString.Length;
      v34 = v37;
      v36 = v21.Buffer;
      v37[0] = v21.Length;
      v18 = v2[7];
      v38 = &v18;
      v11 = v1[144];
      v23 = v1[18];
      v40 = &v23;
      v24[7] = 2;
      v25[1] = 0;
      v27 = 2;
      v29[1] = 0;
      v31 = 2;
      v33[1] = 0;
      v35 = 2;
      v37[1] = 0;
      v39 = 4;
      v41 = 8;
      v14 = *(_BYTE *)(v11 + 93) >> 7;
      v42 = &v14;
      v43 = 1;
      if ( (*(_BYTE *)(v11 + 94) & 7) != 2 || (v12 = 1, *(char *)(v11 + 93) >= 0) )
        v12 = 0;
      v13 = v1[143];
      v15 = v12;
      v44 = &v15;
      v45 = 1;
      v16 = *(_BYTE *)(v13 + 1334);
      v46 = &v16;
      v47 = 1;
      v17 = *(_BYTE *)(v13 + 1332);
      v48 = &v17;
      v49 = 1;
      tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_14004912B, 1, v9, 0x11u, (__int64)v24);
    }
    RtlFreeUnicodeString(&DestinationString);
    RtlFreeUnicodeString(&UnicodeString);
    RtlFreeUnicodeString(&v21);
    RtlFreeUnicodeString(&v22);
  }
}

```

## disassembly

```asm
0x14003dbfc  push    rbp
0x14003dbfe  push    rbx
0x14003dbff  push    rsi
0x14003dc00  push    rdi
0x14003dc01  lea     rbp, [rsp-0A8h]
0x14003dc09  sub     rsp, 1A8h
0x14003dc10  mov     rax, cs:__security_cookie
0x14003dc17  xor     rax, rsp
0x14003dc1a  mov     [rbp+0C0h+var_30], rax
0x14003dc21  mov     rdi, [rcx+40h]
0x14003dc25  xorps   xmm0, xmm0
0x14003dc28  xorps   xmm1, xmm1
0x14003dc2b  xor     esi, esi
0x14003dc2d  mov     rbx, [rdi+208h]
0x14003dc34  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x14003dc39  movups  xmmword ptr [rsp+1C0h+UnicodeString.Length], xmm1
0x14003dc3e  movups  xmmword ptr [rsp+1C0h+var_168.Length], xmm0
0x14003dc43  movups  xmmword ptr [rsp+1C0h+var_158.Length], xmm1
0x14003dc48  cmp     [rdi+208h], rsi
0x14003dc4f  jz      loc_14003DEE5
0x14003dc55  mov     edx, [rbx+0Ch]
0x14003dc58  test    edx, edx
0x14003dc5a  jz      short loc_14003DC6F
0x14003dc5c  mov     r8d, [rbx+4]
0x14003dc60  lea     r9, [rsp+1C0h+DestinationString]
0x14003dc65  mov     rcx, rbx
0x14003dc68  call    ClasspGetUnicodeStringFromAnsiAtOffset
0x14003dc6d  jmp     short loc_14003DC82
0x14003dc6f  xor     edx, edx; SourceString
0x14003dc71  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x14003dc76  call    cs:__imp_RtlInitUnicodeString
0x14003dc7d  nop     dword ptr [rax+rax+00h]
0x14003dc82  mov     edx, [rbx+10h]
0x14003dc85  test    edx, edx
0x14003dc87  jz      short loc_14003DC9C
0x14003dc89  mov     r8d, [rbx+4]
0x14003dc8d  lea     r9, [rsp+1C0h+UnicodeString]
0x14003dc92  mov     rcx, rbx
0x14003dc95  call    ClasspGetUnicodeStringFromAnsiAtOffset
0x14003dc9a  jmp     short loc_14003DCAF
0x14003dc9c  xor     edx, edx; SourceString
0x14003dc9e  lea     rcx, [rsp+1C0h+UnicodeString]; DestinationString
0x14003dca3  call    cs:__imp_RtlInitUnicodeString
0x14003dcaa  nop     dword ptr [rax+rax+00h]
0x14003dcaf  mov     edx, [rbx+14h]
0x14003dcb2  test    edx, edx
0x14003dcb4  jz      short loc_14003DCC9
0x14003dcb6  mov     r8d, [rbx+4]
0x14003dcba  lea     r9, [rsp+1C0h+var_168]
0x14003dcbf  mov     rcx, rbx
0x14003dcc2  call    ClasspGetUnicodeStringFromAnsiAtOffset
0x14003dcc7  jmp     short loc_14003DCDC
0x14003dcc9  xor     edx, edx; SourceString
0x14003dccb  lea     rcx, [rsp+1C0h+var_168]; DestinationString
0x14003dcd0  call    cs:__imp_RtlInitUnicodeString
0x14003dcd7  nop     dword ptr [rax+rax+00h]
0x14003dcdc  mov     edx, [rbx+18h]
0x14003dcdf  test    edx, edx
0x14003dce1  jz      short loc_14003DCF6
0x14003dce3  mov     r8d, [rbx+4]
0x14003dce7  lea     r9, [rsp+1C0h+var_158]
0x14003dcec  mov     rcx, rbx
0x14003dcef  call    ClasspGetUnicodeStringFromAnsiAtOffset
0x14003dcf4  jmp     short loc_14003DD09
0x14003dcf6  xor     edx, edx; SourceString
0x14003dcf8  lea     rcx, [rsp+1C0h+var_158]; DestinationString
0x14003dcfd  call    cs:__imp_RtlInitUnicodeString
0x14003dd04  nop     dword ptr [rax+rax+00h]
0x14003dd09  mov     eax, cs:dword_14004D060
0x14003dd0f  cmp     eax, 5
0x14003dd12  jbe     loc_14003DEA1
0x14003dd18  mov     rdx, 400000000000h
0x14003dd22  call    _tlgKeywordOn
0x14003dd27  test    al, al
0x14003dd29  jz      loc_14003DEA1
0x14003dd2f  mov     rax, [rdi+490h]
0x14003dd36  mov     edx, 2
0x14003dd3b  add     rax, 4
0x14003dd3f  mov     [rbp+0C0h+var_118], 10h
0x14003dd47  mov     [rbp+0C0h+var_120], rax
0x14003dd4b  lea     rax, [rbp+0C0h+var_F8]
0x14003dd4f  mov     [rbp+0C0h+var_110], rax
0x14003dd53  mov     rax, [rsp+1C0h+var_158.Buffer]
0x14003dd58  lea     r8d, [rdx-1]; int
0x14003dd5c  mov     [rbp+0C0h+var_100], rax
0x14003dd60  movzx   eax, [rsp+1C0h+var_158.Length]
0x14003dd65  mov     [rbp+0C0h+var_F8], eax
0x14003dd68  lea     rax, [rbp+0C0h+var_D8]
0x14003dd6c  mov     [rbp+0C0h+var_F0], rax
0x14003dd70  mov     rax, [rsp+1C0h+UnicodeString.Buffer]
0x14003dd75  mov     [rbp+0C0h+var_E0], rax
0x14003dd79  movzx   eax, [rsp+1C0h+UnicodeString.Length]
0x14003dd7e  mov     [rbp+0C0h+var_D8], eax
0x14003dd81  lea     rax, [rbp+0C0h+var_B8]
0x14003dd85  mov     [rbp+0C0h+var_D0], rax
0x14003dd89  mov     rax, [rsp+1C0h+DestinationString.Buffer]
0x14003dd8e  mov     [rbp+0C0h+var_C0], rax
0x14003dd92  movzx   eax, [rsp+1C0h+DestinationString.Length]
0x14003dd97  mov     [rbp+0C0h+var_B8], eax
0x14003dd9a  lea     rax, [rbp+0C0h+var_98]
0x14003dd9e  mov     [rbp+0C0h+var_B0], rax
0x14003dda2  mov     rax, [rsp+1C0h+var_168.Buffer]
0x14003dda7  mov     [rbp+0C0h+var_A0], rax
0x14003ddab  movzx   eax, [rsp+1C0h+var_168.Length]
0x14003ddb0  mov     [rbp+0C0h+var_98], eax
0x14003ddb3  mov     eax, [rbx+1Ch]
0x14003ddb6  mov     [rsp+1C0h+var_18C], eax
0x14003ddba  lea     rax, [rsp+1C0h+var_18C]
0x14003ddbf  mov     [rbp+0C0h+var_90], rax
0x14003ddc3  mov     rax, [rdi+90h]
0x14003ddca  mov     rcx, [rdi+480h]
0x14003ddd1  mov     [rsp+1C0h+var_148], rax
0x14003ddd6  lea     rax, [rsp+1C0h+var_148]
0x14003dddb  mov     [rbp+0C0h+var_80], rax
0x14003dddf  mov     [rbp+0C0h+var_108], rdx
0x14003dde3  mov     [rbp+0C0h+var_F4], esi
0x14003dde6  mov     [rbp+0C0h+var_E8], rdx
0x14003ddea  mov     [rbp+0C0h+var_D4], esi
0x14003dded  mov     [rbp+0C0h+var_C8], rdx
0x14003ddf1  mov     [rbp+0C0h+var_B4], esi
0x14003ddf4  mov     [rbp+0C0h+var_A8], rdx
0x14003ddf8  mov     [rbp+0C0h+var_94], esi
0x14003ddfb  mov     [rbp+0C0h+var_88], 4
0x14003de03  mov     [rbp+0C0h+var_78], 8
0x14003de0b  mov     al, [rcx+5Dh]
0x14003de0e  shr     al, 7
0x14003de11  mov     [rsp+1C0h+var_190], al
0x14003de15  lea     rax, [rsp+1C0h+var_190]
0x14003de1a  mov     [rbp+0C0h+var_70], rax
0x14003de1e  mov     [rbp+0C0h+var_68], r8
0x14003de22  mov     al, [rcx+5Eh]
0x14003de25  and     al, 7
0x14003de27  cmp     al, dl
0x14003de29  jnz     short loc_14003DE35
0x14003de2b  mov     al, [rcx+5Dh]
0x14003de2e  test    al, al
0x14003de30  mov     al, r8b
0x14003de33  js      short loc_14003DE38
0x14003de35  mov     al, sil
0x14003de38  mov     rcx, [rdi+478h]; int
0x14003de3f  lea     rdx, byte_14004912B; int
0x14003de46  mov     [rsp+1C0h+var_18F], al
0x14003de4a  lea     rax, [rsp+1C0h+var_18F]
0x14003de4f  mov     [rbp+0C0h+var_60], rax
0x14003de53  mov     [rbp+0C0h+var_58], r8
0x14003de57  mov     al, [rcx+536h]
0x14003de5d  mov     [rsp+1C0h+var_18E], al
0x14003de61  lea     rax, [rsp+1C0h+var_18E]
0x14003de66  mov     [rbp+0C0h+var_50], rax
0x14003de6a  mov     [rbp+0C0h+var_48], r8
0x14003de6e  mov     al, [rcx+534h]
0x14003de74  mov     [rsp+1C0h+var_18D], al
0x14003de78  lea     rax, [rsp+1C0h+var_18D]
0x14003de7d  mov     [rbp+0C0h+var_40], rax
0x14003de84  lea     rax, [rbp+0C0h+var_140]
0x14003de88  mov     [rsp+1C0h+var_198], rax; __int64
0x14003de8d  mov     [rsp+1C0h+var_1A0], 11h; ULONG
0x14003de95  mov     [rbp+0C0h+var_38], r8
0x14003de9c  call    _tlgWriteTransfer_EtwWriteTransfer
0x14003dea1  lea     rcx, [rsp+1C0h+DestinationString]; UnicodeString
0x14003dea6  call    cs:__imp_RtlFreeUnicodeString
0x14003dead  nop     dword ptr [rax+rax+00h]
0x14003deb2  lea     rcx, [rsp+1C0h+UnicodeString]; UnicodeString
0x14003deb7  call    cs:__imp_RtlFreeUnicodeString
0x14003debe  nop     dword ptr [rax+rax+00h]
0x14003dec3  lea     rcx, [rsp+1C0h+var_168]; UnicodeString
0x14003dec8  call    cs:__imp_RtlFreeUnicodeString
0x14003decf  nop     dword ptr [rax+rax+00h]
0x14003ded4  lea     rcx, [rsp+1C0h+var_158]; UnicodeString
0x14003ded9  call    cs:__imp_RtlFreeUnicodeString
0x14003dee0  nop     dword ptr [rax+rax+00h]
0x14003dee5  mov     rcx, [rbp+0C0h+var_30]
0x14003deec  xor     rcx, rsp; StackCookie
0x14003deef  call    __security_check_cookie
0x14003def4  add     rsp, 1A8h
0x14003defb  pop     rdi
0x14003defc  pop     rsi
0x14003defd  pop     rbx
0x14003defe  pop     rbp
0x14003deff  retn
```
