# CRtSend::SignMessageForNativeProtocol(void)

- ea: `0x18001c688`
- end: `0x18001c880`
- name: `?SignMessageForNativeProtocol@CRtSend@@AEAAJXZ`
- size: `504`
- prototype: `__int64 __fastcall(CRtSend *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001c5f4`

## callees

- `0x180007e10`
- `0x1800087f8`
- `0x180013c74`
- `0x180019de4`
- `0x18001bf20`
- `0x18001c188`
- `0x18001c688`
- `0x180023c4e`
- `0x180023ca0`

## pseudocode

```c
__int64 __fastcall CRtSend::SignMessageForNativeProtocol(CRtSend *this)
{
  unsigned int v2; // edi
  int v3; // esi
  unsigned __int16 v4; // r8
  _DWORD *v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  int v10; // edx
  int v11; // eax
  bool v12; // zf
  unsigned int v13; // eax
  size_t Size[2]; // [rsp+30h] [rbp-438h] BYREF
  unsigned __int8 Src[1040]; // [rsp+40h] [rbp-428h] BYREF

  v2 = *((_DWORD *)this + 218) & 0xF;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 27, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids, v2);
  if ( (v2 & 2) != 0 )
  {
    v3 = CRtSend::SignMessage10(this);
    if ( v3 < 0 )
    {
      v4 = 412;
LABEL_7:
      LogMsgHR(v3, (wchar_t *)L"rt/CRtSend", v4);
      return (unsigned int)v3;
    }
  }
  else
  {
    v6 = (_DWORD *)*((_QWORD *)this + 244);
    *((_DWORD *)this + 94) = 4;
    *v6 = 0;
  }
  LODWORD(Size[0]) = 1040;
  if ( v2 != 2 )
  {
    if ( (v2 & 8) != 0 )
    {
      v3 = SignMessage30(
             *((_QWORD *)this + 93),
             *((_QWORD *)this + 104),
             (char *)this + 40,
             (char *)this + 864,
             (char *)this + 664);
      if ( v3 < 0 )
      {
        v4 = 415;
        goto LABEL_7;
      }
    }
    if ( (v2 & 4) != 0 )
    {
      v7 = CRtSend::SignMessage20(this, Src, (unsigned int *)Size);
      v8 = v7;
      if ( v7 < 0 )
      {
        LogMsgHR(v7, (wchar_t *)L"rt/CRtSend", 0x1A1u);
        return v8;
      }
      if ( LODWORD(Size[0]) )
      {
        v9 = *((unsigned int *)this + 94);
        if ( (unsigned int)(v9 + LODWORD(Size[0])) > 0x410 )
        {
          LogMsgHR(-1072824319, (wchar_t *)L"rt/CRtSend", 0xAAu);
        }
        else
        {
          memcpy_0((char *)this + v9 + 912, Src, LODWORD(Size[0]));
          v10 = Size[0];
          v11 = 0;
          v12 = LODWORD(Size[0]) + *((_DWORD *)this + 94) == 0;
          *((_DWORD *)this + 94) += LODWORD(Size[0]);
          if ( !v12 && !*((_DWORD *)this + 82) )
          {
            v13 = mqwcslen(**((const wchar_t ***)this + 37));
            v10 = Size[0];
            v11 = 2 * v13 + 6;
          }
          *((_QWORD *)this + 39) = (char *)this + 788;
          *((_DWORD *)this + 197) = v10 + ((v11 + 3) & 0xFFFFFFFC);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c688  mov     [rsp+arg_8], rbx
0x18001c68d  mov     [rsp+arg_10], rsi
0x18001c692  push    rdi
0x18001c693  sub     rsp, 460h
0x18001c69a  mov     rax, cs:__security_cookie
0x18001c6a1  xor     rax, rsp
0x18001c6a4  mov     [rsp+468h+var_18], rax
0x18001c6ac  mov     edi, [rcx+368h]
0x18001c6b2  mov     rbx, rcx
0x18001c6b5  and     edi, 0Fh
0x18001c6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c6bf  lea     rax, WPP_GLOBAL_Control
0x18001c6c6  cmp     rcx, rax
0x18001c6c9  jz      short loc_18001C6EF
0x18001c6cb  test    byte ptr [rcx+10Ch], 4
0x18001c6d2  jz      short loc_18001C6EF
0x18001c6d4  mov     rcx, [rcx+100h]
0x18001c6db  lea     r8, WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids
0x18001c6e2  mov     edx, 1Bh
0x18001c6e7  mov     r9d, edi
0x18001c6ea  call    WPP_SF_d
0x18001c6ef  test    dil, 2
0x18001c6f3  jz      short loc_18001C71E
0x18001c6f5  mov     rcx, rbx; this
0x18001c6f8  call    ?SignMessage10@CRtSend@@AEAAJXZ; CRtSend::SignMessage10(void)
0x18001c6fd  mov     esi, eax
0x18001c6ff  test    eax, eax
0x18001c701  jns     short loc_18001C733
0x18001c703  mov     r8d, 19Ch; unsigned __int16
0x18001c709  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001c710  mov     ecx, esi; int
0x18001c712  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001c717  mov     eax, esi
0x18001c719  jmp     loc_18001C85B
0x18001c71e  mov     rax, [rbx+7A0h]
0x18001c725  xor     ecx, ecx
0x18001c727  mov     dword ptr [rbx+178h], 4
0x18001c731  mov     [rax], ecx
0x18001c733  mov     dword ptr [rsp+468h+Size], 410h
0x18001c73b  mov     r8, rbx
0x18001c73e  cmp     edi, 2
0x18001c741  jz      loc_18001C859
0x18001c747  test    dil, 8
0x18001c74b  jz      short loc_18001C785
0x18001c74d  mov     rdx, [rbx+340h]
0x18001c754  lea     rax, [rbx+298h]
0x18001c75b  mov     rcx, [rbx+2E8h]
0x18001c762  lea     r9, [rbx+360h]
0x18001c769  add     r8, 28h ; '('
0x18001c76d  mov     [rsp+468h+var_448], rax
0x18001c772  call    ?SignMessage30@@YAJPEAVRTSecurityContextBase@@PEB_WPEAVCACSendParameters@@AEAV?$AP@E@@PEAK@Z; SignMessage30(RTSecurityContextBase *,wchar_t const *,CACSendParameters *,AP<uchar> &,ulong *)
0x18001c777  mov     esi, eax
0x18001c779  test    eax, eax
0x18001c77b  jns     short loc_18001C785
0x18001c77d  mov     r8d, 19Fh
0x18001c783  jmp     short loc_18001C709
0x18001c785  test    dil, 4
0x18001c789  jz      loc_18001C859
0x18001c78f  lea     r8, [rsp+468h+Size]; unsigned int *
0x18001c794  mov     rcx, rbx; this
0x18001c797  lea     rdx, [rsp+468h+Src]; unsigned __int8 *
0x18001c79c  call    ?SignMessage20@CRtSend@@AEAAJPEAEPEAK@Z; CRtSend::SignMessage20(uchar *,ulong *)
0x18001c7a1  mov     edi, eax
0x18001c7a3  test    eax, eax
0x18001c7a5  jns     short loc_18001C7C2
0x18001c7a7  mov     r8d, 1A1h; unsigned __int16
0x18001c7ad  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001c7b4  mov     ecx, eax; int
0x18001c7b6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001c7bb  mov     eax, edi
0x18001c7bd  jmp     loc_18001C85B
0x18001c7c2  mov     ecx, dword ptr [rsp+468h+Size]
0x18001c7c6  test    ecx, ecx
0x18001c7c8  jz      loc_18001C859
0x18001c7ce  mov     edx, [rbx+178h]
0x18001c7d4  lea     eax, [rdx+rcx]
0x18001c7d7  cmp     eax, 410h
0x18001c7dc  ja      short loc_18001C842
0x18001c7de  mov     r8d, ecx; Size
0x18001c7e1  lea     rcx, [rdx+390h]
0x18001c7e8  add     rcx, rbx; void *
0x18001c7eb  lea     rdx, [rsp+468h+Src]; Src
0x18001c7f0  call    memcpy_0
0x18001c7f5  mov     edx, dword ptr [rsp+468h+Size]
0x18001c7f9  mov     eax, 0
0x18001c7fe  add     [rbx+178h], edx
0x18001c804  jz      short loc_18001C828
0x18001c806  cmp     [rbx+148h], eax
0x18001c80c  jnz     short loc_18001C828
0x18001c80e  mov     rcx, [rbx+128h]
0x18001c815  mov     rcx, [rcx]; wchar_t *
0x18001c818  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001c81d  mov     edx, dword ptr [rsp+468h+Size]
0x18001c821  lea     eax, ds:6[rax*2]
0x18001c828  add     eax, 3
0x18001c82b  lea     rcx, [rbx+314h]
0x18001c832  and     eax, 0FFFFFFFCh
0x18001c835  mov     [rbx+138h], rcx
0x18001c83c  add     eax, edx
0x18001c83e  mov     [rcx], eax
0x18001c840  jmp     short loc_18001C859
0x18001c842  mov     r8d, 0AAh; unsigned __int16
0x18001c848  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x18001c84f  mov     ecx, 0C00E0001h; int
0x18001c854  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001c859  xor     eax, eax
0x18001c85b  mov     rcx, [rsp+468h+var_18]
0x18001c863  xor     rcx, rsp; StackCookie
0x18001c866  call    __security_check_cookie
0x18001c86b  lea     r11, [rsp+468h+var_8]
0x18001c873  mov     rbx, [r11+18h]
0x18001c877  mov     rsi, [r11+20h]
0x18001c87b  mov     rsp, r11
0x18001c87e  pop     rdi
0x18001c87f  retn
```
