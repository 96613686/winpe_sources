# PushMessage::TrimContentType(void)

- ea: `0x18001adf8`
- end: `0x18001b06f`
- name: `?TrimContentType@PushMessage@@QEAAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(PushMessage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180016110`

## callees

- `0x1800039f0`
- `0x18000c504`
- `0x1800127c4`
- `0x180013528`
- `0x180017384`
- `0x18001adf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ae98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ae51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b03f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b03f`
- `DMCmnUtils!CopyString` at `0x18001ae8d`
- `DMCmnUtils!CopyString` at `0x18001ae8d`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001af7f`
- `DMCmnUtils!InvStrCmpNIW` at `0x18001af7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushMessage::TrimContentType(PushMessage *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  signed int v3; // ebx
  __int64 v4; // rcx
  unsigned __int16 *v5; // rdi
  __int64 v6; // rcx
  _WORD *v7; // rax
  __int64 v8; // rsi
  const unsigned __int16 *v9; // r15
  unsigned __int16 *v10; // rcx
  int v11; // r8d
  unsigned __int16 v12; // ax
  int v13; // eax
  __int64 v14; // r8
  unsigned __int16 *v15; // rdx
  unsigned __int16 v16; // ax
  HLOCAL hMem; // [rsp+20h] [rbp-60h] BYREF
  unsigned int v19; // [rsp+28h] [rbp-58h] BYREF
  unsigned int v20; // [rsp+2Ch] [rbp-54h] BYREF
  unsigned int v21; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int16 *v23; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v24; // [rsp+48h] [rbp-38h] BYREF
  char v25; // [rsp+50h] [rbp-30h]
  unsigned __int16 v26[16]; // [rsp+58h] [rbp-28h] BYREF

  *(_OWORD *)v26 = *(_OWORD *)L"Content-Type";
  *(_OWORD *)&v26[5] = *(_OWORD *)L"nt-Type";
  hMem = 0;
  v19 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v24 = (unsigned __int16 *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v25 = 1;
  if ( *((_DWORD *)this + 4) > 2u && (v4 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL)) != 0 )
  {
    if ( *(_DWORD *)v4 == 1 )
      v3 = CopyString(*(const unsigned __int16 **)(v4 + 16), 0xFFFFFFFF, (unsigned __int16 **)&hMem);
    else
      v3 = -2147024883;
  }
  else
  {
    v3 = -2147023728;
  }
  LeaveCriticalSection(v2);
  v5 = (unsigned __int16 *)hMem;
  if ( v3 >= 0 )
  {
    v23 = (unsigned __int16 *)hMem;
    v22 = (unsigned __int16 *)hMem;
    if ( hMem )
    {
      v6 = 0x7FFFFFFF;
      v7 = hMem;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v6;
      }
      while ( v6 );
      v3 = v6 == 0 ? 0x80070057 : 0;
      v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
      if ( v6 )
      {
        v9 = (const unsigned __int16 *)((char *)hMem + 2 * v8);
        while ( 1 )
        {
          if ( !(unsigned int)FindEndOfHeader((const unsigned __int16 **)&v23, v9, &v19) )
            goto LABEL_33;
          v10 = v5;
          v11 = 0;
          if ( v19 )
          {
            while ( 1 )
            {
              v12 = *v10++;
              if ( v12 == 58 )
                break;
              if ( ++v11 >= v19 )
                goto LABEL_18;
            }
            v24 = v10;
            v20 = v10 - v5 - 1;
            v21 = v19 - v20;
            if ( (unsigned int)Trim((const unsigned __int16 **)&v22, &v20) )
            {
              if ( v20 == 12 && !InvStrCmpNIW(v22, v26, 0xCu) )
                break;
            }
          }
LABEL_18:
          v5 = v23;
          v22 = v23;
        }
        v13 = Trim((const unsigned __int16 **)&v24, &v21);
        v14 = v13 != 0 ? v21 : 0;
        v15 = v24;
        if ( !v24 )
          goto LABEL_33;
        v16 = *v24;
        if ( !*v24 )
          goto LABEL_33;
        while ( v16 != 59 && v16 != 32 && v16 != 13 && v16 != 10 )
        {
          ++v15;
          v14 = (unsigned int)(v14 - 1);
          v16 = *v15;
          if ( !*v15 )
            goto LABEL_33;
        }
        if ( v16 == 13
          || v16 == 10
          || (*v15 = 0, v3 = StringCchCatW((unsigned __int16 *)hMem, v8 + 1, &v15[v14]), v3 >= 0) )
        {
LABEL_33:
          v3 = PersistObject::Set((__int64)this, 2u, (const unsigned __int16 *)hMem);
        }
        v5 = (unsigned __int16 *)hMem;
      }
    }
    else
    {
      v3 = -2147024809;
    }
  }
  LocalFree(v5);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001adf8  mov     [rsp-28h+arg_8], rbx
0x18001adfd  mov     [rsp-28h+arg_10], rsi
0x18001ae02  push    rbp
0x18001ae03  push    rdi
0x18001ae04  push    r12
0x18001ae06  push    r14
0x18001ae08  push    r15
0x18001ae0a  mov     rbp, rsp
0x18001ae0d  sub     rsp, 80h
0x18001ae14  mov     rax, cs:__security_cookie
0x18001ae1b  xor     rax, rsp
0x18001ae1e  mov     [rbp+var_8], rax
0x18001ae22  mov     r14, rcx
0x18001ae25  movups  xmm0, xmmword ptr cs:aContentType; "Content-Type"
0x18001ae2c  movups  xmmword ptr [rbp+var_28], xmm0
0x18001ae30  movups  xmm1, xmmword ptr cs:aContentType+0Ah; "nt-Type"
0x18001ae37  movups  xmmword ptr [rbp+var_28+0Ah], xmm1
0x18001ae3b  xor     r12d, r12d
0x18001ae3e  mov     [rbp+hMem], r12
0x18001ae42  mov     [rbp+var_58], r12d
0x18001ae46  lea     rdi, [rcx+20h]
0x18001ae4a  mov     [rbp+var_38], rdi
0x18001ae4e  mov     rcx, rdi; lpCriticalSection
0x18001ae51  call    cs:__imp_EnterCriticalSection
0x18001ae57  mov     [rbp+var_30], 1
0x18001ae5b  cmp     dword ptr [r14+10h], 2
0x18001ae60  ja      short loc_18001AE69
0x18001ae62  mov     ebx, 80070490h
0x18001ae67  jmp     short loc_18001AE95
0x18001ae69  mov     rax, [r14+8]
0x18001ae6d  mov     rcx, [rax+10h]
0x18001ae71  test    rcx, rcx
0x18001ae74  jz      short loc_18001AE62
0x18001ae76  cmp     dword ptr [rcx], 1
0x18001ae79  jz      short loc_18001AE82
0x18001ae7b  mov     ebx, 8007000Dh
0x18001ae80  jmp     short loc_18001AE95
0x18001ae82  lea     r8, [rbp+hMem]
0x18001ae86  or      edx, 0FFFFFFFFh
0x18001ae89  mov     rcx, [rcx+10h]
0x18001ae8d  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18001ae93  mov     ebx, eax
0x18001ae95  mov     rcx, rdi; lpCriticalSection
0x18001ae98  call    cs:__imp_LeaveCriticalSection
0x18001ae9e  mov     rdi, [rbp+hMem]
0x18001aea2  test    ebx, ebx
0x18001aea4  js      loc_18001B03C
0x18001aeaa  mov     [rbp+var_40], rdi
0x18001aeae  mov     [rbp+var_48], rdi
0x18001aeb2  test    rdi, rdi
0x18001aeb5  jz      loc_18001B037
0x18001aebb  mov     edx, 7FFFFFFFh
0x18001aec0  mov     ecx, edx
0x18001aec2  mov     rax, rdi
0x18001aec5  cmp     [rax], r12w
0x18001aec9  jz      short loc_18001AED5
0x18001aecb  add     rax, 2
0x18001aecf  sub     rcx, 1
0x18001aed3  jnz     short loc_18001AEC5
0x18001aed5  mov     rax, rcx
0x18001aed8  neg     rax
0x18001aedb  sbb     ebx, ebx
0x18001aedd  not     ebx
0x18001aedf  and     ebx, 80070057h
0x18001aee5  mov     rax, rcx
0x18001aee8  sub     rdx, rcx
0x18001aeeb  neg     rax
0x18001aeee  sbb     rsi, rsi
0x18001aef1  and     rsi, rdx
0x18001aef4  test    rcx, rcx
0x18001aef7  jz      loc_18001B03C
0x18001aefd  lea     r15, [rdi+rsi*2]
0x18001af01  lea     r8, [rbp+var_58]; unsigned int *
0x18001af05  mov     rdx, r15; unsigned __int16 *
0x18001af08  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x18001af0c  call    ?FindEndOfHeader@@YAHPEAPEBGPEBGPEAK@Z; FindEndOfHeader(ushort const * *,ushort const *,ulong *)
0x18001af11  test    eax, eax
0x18001af13  jz      loc_18001B01E
0x18001af19  mov     rcx, rdi
0x18001af1c  mov     r8d, r12d
0x18001af1f  mov     edx, [rbp+var_58]
0x18001af22  test    edx, edx
0x18001af24  jz      short loc_18001AF3B
0x18001af26  movzx   eax, word ptr [rcx]
0x18001af29  add     rcx, 2
0x18001af2d  cmp     ax, 3Ah ; ':'
0x18001af31  jz      short loc_18001AF45
0x18001af33  inc     r8d
0x18001af36  cmp     r8d, edx
0x18001af39  jb      short loc_18001AF26
0x18001af3b  mov     rdi, [rbp+var_40]
0x18001af3f  mov     [rbp+var_48], rdi
0x18001af43  jmp     short loc_18001AF01
0x18001af45  mov     [rbp+var_38], rcx
0x18001af49  sub     rcx, rdi
0x18001af4c  sar     rcx, 1
0x18001af4f  lea     eax, [rcx-1]
0x18001af52  mov     [rbp+var_54], eax
0x18001af55  sub     edx, eax
0x18001af57  mov     [rbp+var_50], edx
0x18001af5a  lea     rdx, [rbp+var_54]; unsigned int *
0x18001af5e  lea     rcx, [rbp+var_48]; unsigned __int16 **
0x18001af62  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001af67  test    eax, eax
0x18001af69  jz      short loc_18001AF3B
0x18001af6b  cmp     [rbp+var_54], 0Ch
0x18001af6f  jnz     short loc_18001AF3B
0x18001af71  mov     r8d, 0Ch
0x18001af77  lea     rdx, [rbp+var_28]
0x18001af7b  mov     rcx, [rbp+var_48]
0x18001af7f  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x18001af85  test    eax, eax
0x18001af87  jnz     short loc_18001AF3B
0x18001af89  lea     rdx, [rbp+var_50]; unsigned int *
0x18001af8d  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x18001af91  call    ?Trim@@YAHPEAPEBGPEAK@Z; Trim(ushort const * *,ulong *)
0x18001af96  neg     eax
0x18001af98  sbb     r8d, r8d
0x18001af9b  and     r8d, [rbp+var_50]
0x18001af9f  mov     rdx, [rbp+var_38]
0x18001afa3  test    rdx, rdx
0x18001afa6  jz      short loc_18001B01E
0x18001afa8  movzx   eax, word ptr [rdx]
0x18001afab  test    ax, ax
0x18001afae  jz      short loc_18001B01E
0x18001afb0  mov     r10d, 0Dh
0x18001afb6  lea     r11d, [r10-3]
0x18001afba  movzx   ecx, ax
0x18001afbd  mov     r9d, 3Bh ; ';'
0x18001afc3  cmp     r9w, ax
0x18001afc7  jz      short loc_18001AFF7
0x18001afc9  mov     r9d, 20h ; ' '
0x18001afcf  cmp     r9w, ax
0x18001afd3  jz      short loc_18001AFF2
0x18001afd5  cmp     r10w, ax
0x18001afd9  jz      short loc_18001AFF2
0x18001afdb  cmp     r11w, ax
0x18001afdf  jz      short loc_18001AFF2
0x18001afe1  add     rdx, 2
0x18001afe5  dec     r8d
0x18001afe8  movzx   eax, word ptr [rdx]
0x18001afeb  test    ax, ax
0x18001afee  jnz     short loc_18001AFBA
0x18001aff0  jmp     short loc_18001B01E
0x18001aff2  test    cx, cx
0x18001aff5  jz      short loc_18001B01E
0x18001aff7  cmp     r10w, cx
0x18001affb  jz      short loc_18001B01E
0x18001affd  cmp     r11w, cx
0x18001b001  jz      short loc_18001B01E
0x18001b003  mov     [rdx], r12w
0x18001b007  lea     r8, [rdx+r8*2]; unsigned __int16 *
0x18001b00b  lea     rdx, [rsi+1]; unsigned __int64
0x18001b00f  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18001b013  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b018  mov     ebx, eax
0x18001b01a  test    eax, eax
0x18001b01c  js      short loc_18001B031
0x18001b01e  mov     r8, [rbp+hMem]
0x18001b022  mov     edx, 2
0x18001b027  mov     rcx, r14
0x18001b02a  call    ?Set@PersistObject@@QEAAJW4PERSIST_OBJECT_MEMBER_ID@1@PEBG@Z; PersistObject::Set(PersistObject::PERSIST_OBJECT_MEMBER_ID,ushort const *)
0x18001b02f  mov     ebx, eax
0x18001b031  mov     rdi, [rbp+hMem]
0x18001b035  jmp     short loc_18001B03C
0x18001b037  mov     ebx, 80070057h
0x18001b03c  mov     rcx, rdi; hMem
0x18001b03f  call    cs:__imp_LocalFree
0x18001b045  mov     eax, ebx
0x18001b047  mov     rcx, [rbp+var_8]
0x18001b04b  xor     rcx, rsp; StackCookie
0x18001b04e  call    __security_check_cookie
0x18001b053  lea     r11, [rsp+80h+var_s0]
0x18001b05b  mov     rbx, [r11+38h]
0x18001b05f  mov     rsi, [r11+40h]
0x18001b063  mov     rsp, r11
0x18001b066  pop     r15
0x18001b068  pop     r14
0x18001b06a  pop     r12
0x18001b06c  pop     rdi
0x18001b06d  pop     rbp
0x18001b06e  retn
```
