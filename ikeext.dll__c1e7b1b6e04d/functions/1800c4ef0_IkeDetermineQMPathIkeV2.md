# IkeDetermineQMPathIkeV2

- ea: `0x1800c4ef0`
- end: `0x1800c5375`
- name: `IkeDetermineQMPathIkeV2`
- size: `1157`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800c4c6c`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180008388`
- `0x1800087f0`
- `0x180024820`
- `0x180025d88`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x1800c4ef0`
- `0x1800c6700`
- `0x1800c6754`
- `0x1800e9034`
- `0x1800f9600`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x1800c4fb8`
- `WS2_32!__imp_ntohl` at `0x1800c5114`
- `WS2_32!__imp_ntohl` at `0x1800c4fb8`
- `WS2_32!__imp_ntohl` at `0x1800c5114`

## string_xrefs

- `0x1800c506e`: `IKEv2 ENCRYPT FRAGMENT PAYLOAD Received in Quick Mode Negotiation.             Setting path as PROCESS_PATH_FRAG`
- `0x1800c4f25`: `IkeDetermineQMPathIkeV2`
- `0x1800c5333`: `IkeDetermineQMPathIkeV2`
- `0x1800c533f`: `IkeDetermineQMPathIkeV2`
- `0x1800c51b3`: `Switching to INPLACE_REKEY path`

## pseudocode

```c
__int64 __fastcall IkeDetermineQMPathIkeV2(__int64 a1, __int64 *a2, _DWORD *a3)
{
  __int64 IsNewQMSAAllowed; // r15
  __int64 v7; // rbx
  _BYTE *v8; // r14
  __int64 v9; // rcx
  u_long v10; // edi
  __int64 v11; // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rcx
  u_long v20; // eax
  __int64 v21; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v23; // rcx
  int TlsMmLuid; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  _DWORD *v30; // r14
  __int64 v31; // rdi
  __int64 v32; // rbx
  __int64 v33; // rcx
  int v34; // eax
  __int64 v35; // rcx
  __int64 v36; // rax
  int v37; // r8d
  int v38; // r9d
  __int64 v40; // [rsp+30h] [rbp-69h] BYREF
  __int64 v41; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v42[2]; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v43[32]; // [rsp+50h] [rbp-49h] BYREF
  __int64 *v44; // [rsp+70h] [rbp-29h]
  __int64 v45; // [rsp+78h] [rbp-21h]
  _BYTE v46[16]; // [rsp+80h] [rbp-19h] BYREF
  const char *v47; // [rsp+90h] [rbp-9h]
  __int64 v48; // [rsp+98h] [rbp-1h]
  __int64 *v49; // [rsp+A0h] [rbp+7h]
  __int64 v50; // [rsp+A8h] [rbp+Fh]

  LODWORD(v41) = 0;
  LODWORD(v40) = 0;
  IsNewQMSAAllowed = 0;
  TraceLogHelper("IkeDetermineQMPathIkeV2", 1);
  if ( (unsigned int)IkeIsIkeV2QmPacketDupe(a1, a2) )
  {
    a3[4] = 3;
  }
  else if ( IkeFindPayloadInPacket(a2, 0x29u, &v40)
         || (*(_BYTE *)(*a2 + 19) & 0x20) == 0
         || (v40 = 0,
             IsNewQMSAAllowed = IkeCopyIncomingData(&v40, (__int64)a2, 8u),
             NtohTransformIkeV2(&v40),
             HIWORD(v40) > 0x3FFFu) )
  {
    v7 = *a2;
    v8 = (_BYTE *)(*a2 + 19);
    v10 = ntohl(*(_DWORD *)(*a2 + 20));
    if ( *(_BYTE *)(v7 + 16) != 53 || (*v8 & 4) != 0 )
    {
      if ( (*(_BYTE *)(a1 + 592) & 1) != 0 && (*v8 & 0x20) != 0 && *(_DWORD *)(*(_QWORD *)(a1 + 616) + 4LL) == 6 )
      {
        v19 = *(_QWORD *)(a1 + 976);
        if ( v19 )
        {
          if ( !*(_DWORD *)(v19 + 100) )
          {
            v20 = *(_DWORD *)(*(_QWORD *)(v19 + 296) + 20LL);
            if ( (*(_BYTE *)(v19 + 324) & 2) == 0 )
              v20 = ntohl(v20);
            if ( v10 == v20 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                TlsPeerAddr = IkeGetTlsPeerAddr(v19);
                TlsMmLuid = IkeGetTlsMmLuid(v23);
                WPP_SF_iS(
                  v21,
                  21,
                  (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids,
                  TlsMmLuid,
                  TlsPeerAddr);
              }
              if ( (unsigned int)dword_180173278 > 4 )
              {
                v40 = IkeGetTlsMmLuid(v19);
                v44 = &v40;
                v45 = 8;
                v26 = IkeGetTlsPeerAddr(v25);
                tlgCreate1Sz_wchar_t(v46, v26);
                v48 = 32;
                v49 = v42;
                v47 = "Switching to INPLACE_REKEY path";
                v42[0] = a1;
                v50 = 8;
                tlgWriteTransfer_EtwEventWriteTransfer(
                  (unsigned int)&dword_180173278,
                  (unsigned int)&dword_18015C084,
                  v27,
                  v28,
                  6,
                  (__int64)v43);
              }
              a3[1] |= 1u;
              a3[4] = 5;
            }
          }
        }
      }
      IsNewQMSAAllowed = IkeCheckForMMSAIkeV2(a2, &v41);
      if ( !IsNewQMSAAllowed )
      {
        if ( (_DWORD)v41 )
          a3[4] = 5;
        if ( *a3 )
        {
          if ( (*v8 & 0x20) == 0 || (v30 = a3 + 4, a3[4] == 5) )
          {
            IsNewQMSAAllowed = IkeIsNewQMSAAllowed(a1, a2, a3);
            v30 = a3 + 4;
            if ( IsNewQMSAAllowed )
              goto LABEL_49;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v31 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v32 = IkeGetTlsPeerAddr(v29);
              v34 = IkeGetTlsMmLuid(v33);
              WPP_SF_iS(v31, 22, (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids, v34, v32);
            }
            if ( (unsigned int)dword_180173278 > 4 )
            {
              v42[0] = IkeGetTlsMmLuid(v29);
              v44 = v42;
              v45 = 8;
              v36 = IkeGetTlsPeerAddr(v35);
              tlgCreate1Sz_wchar_t(v46, v36);
              v48 = 38;
              v47 = "Received new QM as response. Dropping";
              tlgWriteTransfer_EtwEventWriteTransfer(
                (unsigned int)&dword_180173278,
                (unsigned int)qword_18015C008,
                v37,
                v38,
                5,
                (__int64)v43);
            }
            a3[1] |= 8u;
            *v30 = 4;
          }
        }
        else
        {
          v30 = a3 + 4;
        }
        if ( !*v30 )
          *v30 = 1;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v12 = IkeGetTlsPeerAddr(v9);
        v14 = IkeGetTlsMmLuid(v13);
        WPP_SF_iSq(v11, 20, (unsigned int)WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids, v14, v12, a1);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v40 = IkeGetTlsMmLuid(v9);
        v44 = &v40;
        v45 = 8;
        v16 = IkeGetTlsPeerAddr(v15);
        tlgCreate1Sz_wchar_t(v46, v16);
        v48 = 113;
        v49 = &v41;
        v47 = "IKEv2 ENCRYPT FRAGMENT PAYLOAD Received in Quick Mode Negotiation.             Setting path as PROCESS_PATH_FRAG";
        v41 = a1;
        v50 = 8;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)byte_18015C043,
          v17,
          v18,
          6,
          (__int64)v43);
      }
      a3[4] = 2;
    }
  }
  else
  {
    a3[4] = 6;
  }
LABEL_49:
  TraceLogHelper("IkeDetermineQMPathIkeV2", 0);
  return IkeReturnError(IsNewQMSAAllowed, "IkeDetermineQMPathIkeV2");
}

```

## disassembly

```asm
0x1800c4ef0  mov     [rsp-8+arg_18], rbx
0x1800c4ef5  push    rbp
0x1800c4ef6  push    rsi
0x1800c4ef7  push    rdi
0x1800c4ef8  push    r12
0x1800c4efa  push    r13
0x1800c4efc  push    r14
0x1800c4efe  push    r15
0x1800c4f00  lea     rbp, [rsp-27h]
0x1800c4f05  sub     rsp, 0C0h
0x1800c4f0c  mov     rax, cs:__security_cookie
0x1800c4f13  xor     rax, rsp
0x1800c4f16  mov     [rbp+57h+var_40], rax
0x1800c4f1a  xor     ebx, ebx
0x1800c4f1c  mov     r12, rdx
0x1800c4f1f  mov     r13, rcx
0x1800c4f22  mov     dword ptr [rbp+57h+var_B8], ebx
0x1800c4f25  lea     rcx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c4f2c  mov     dword ptr [rbp+57h+var_C0], ebx
0x1800c4f2f  mov     rsi, r8
0x1800c4f32  mov     r15d, ebx
0x1800c4f35  lea     edx, [rbx+1]
0x1800c4f38  call    TraceLogHelper
0x1800c4f3d  mov     rdx, r12
0x1800c4f40  mov     rcx, r13
0x1800c4f43  call    IkeIsIkeV2QmPacketDupe
0x1800c4f48  test    eax, eax
0x1800c4f4a  jz      short loc_1800C4F58
0x1800c4f4c  mov     dword ptr [rsi+10h], 3
0x1800c4f53  jmp     loc_1800C5331
0x1800c4f58  mov     edx, 29h ; ')'
0x1800c4f5d  lea     r8, [rbp+57h+var_C0]
0x1800c4f61  mov     rcx, r12
0x1800c4f64  call    IkeFindPayloadInPacket
0x1800c4f69  test    rax, rax
0x1800c4f6c  jnz     short loc_1800C4FB1
0x1800c4f6e  mov     rax, [r12]
0x1800c4f72  test    byte ptr [rax+13h], 20h
0x1800c4f76  jz      short loc_1800C4FB1
0x1800c4f78  mov     r8d, 8
0x1800c4f7e  mov     [rbp+57h+var_C0], rbx
0x1800c4f82  mov     rdx, r12
0x1800c4f85  lea     rcx, [rbp+57h+var_C0]; void *
0x1800c4f89  call    IkeCopyIncomingData
0x1800c4f8e  lea     rcx, [rbp+57h+var_C0]
0x1800c4f92  mov     r15, rax
0x1800c4f95  call    NtohTransformIkeV2
0x1800c4f9a  mov     eax, 3FFFh
0x1800c4f9f  cmp     word ptr [rbp+57h+var_C0+6], ax
0x1800c4fa3  ja      short loc_1800C4FB1
0x1800c4fa5  mov     dword ptr [rsi+10h], 6
0x1800c4fac  jmp     loc_1800C5331
0x1800c4fb1  mov     rbx, [r12]
0x1800c4fb5  mov     ecx, [rbx+14h]; netlong
0x1800c4fb8  call    cs:__imp_ntohl
0x1800c4fbe  cmp     byte ptr [rbx+10h], 35h ; '5'
0x1800c4fc2  lea     r14, [rbx+13h]
0x1800c4fc6  mov     edi, eax
0x1800c4fc8  jnz     loc_1800C50B5
0x1800c4fce  test    byte ptr [r14], 4
0x1800c4fd2  jnz     loc_1800C50B5
0x1800c4fd8  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c4fdf  lea     rax, WPP_GLOBAL_Control
0x1800c4fe6  cmp     rdi, rax
0x1800c4fe9  jz      short loc_1800C5029
0x1800c4feb  cmp     byte ptr [rdi+19h], 4
0x1800c4fef  jb      short loc_1800C5029
0x1800c4ff1  test    byte ptr [rdi+1Ch], 10h
0x1800c4ff5  jz      short loc_1800C5029
0x1800c4ff7  mov     rdi, [rdi+10h]
0x1800c4ffb  call    IkeGetTlsPeerAddr
0x1800c5000  mov     rbx, rax
0x1800c5003  call    IkeGetTlsMmLuid
0x1800c5008  mov     r9, rax
0x1800c500b  mov     [rsp+0F0h+var_C8], r13
0x1800c5010  mov     edx, 14h
0x1800c5015  mov     [rsp+0F0h+var_D0], rbx
0x1800c501a  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5021  mov     rcx, rdi
0x1800c5024  call    WPP_SF_iSq
0x1800c5029  mov     eax, cs:dword_180173278
0x1800c502f  cmp     eax, 4
0x1800c5032  jbe     short loc_1800C50A9
0x1800c5034  call    IkeGetTlsMmLuid
0x1800c5039  mov     [rbp+57h+var_C0], rax
0x1800c503d  lea     rax, [rbp+57h+var_C0]
0x1800c5041  mov     [rbp+57h+var_80], rax
0x1800c5045  mov     [rbp+57h+var_78], 8
0x1800c504d  call    IkeGetTlsPeerAddr
0x1800c5052  mov     rdx, rax
0x1800c5055  lea     rcx, [rbp+57h+var_70]
0x1800c5059  call    _tlgCreate1Sz_wchar_t
0x1800c505e  lea     rax, [rbp+57h+var_B8]
0x1800c5062  mov     [rbp+57h+var_58], 71h ; 'q'
0x1800c506a  mov     [rbp+57h+var_50], rax
0x1800c506e  lea     rcx, aIkev2EncryptFr_0; "IKEv2 ENCRYPT FRAGMENT PAYLOAD Received"...
0x1800c5075  lea     rax, [rbp+57h+var_A0]
0x1800c5079  mov     [rbp+57h+var_60], rcx
0x1800c507d  mov     [rsp+0F0h+var_C8], rax
0x1800c5082  lea     rdx, byte_18015C043
0x1800c5089  lea     rcx, dword_180173278
0x1800c5090  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800c5098  mov     [rbp+57h+var_B8], r13
0x1800c509c  mov     [rbp+57h+var_48], 8
0x1800c50a4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c50a9  mov     dword ptr [rsi+10h], 2
0x1800c50b0  jmp     loc_1800C5331
0x1800c50b5  test    byte ptr [r13+250h], 1
0x1800c50bd  lea     rdx, WPP_GLOBAL_Control
0x1800c50c4  jz      loc_1800C51F9
0x1800c50ca  test    byte ptr [r14], 20h
0x1800c50ce  jz      loc_1800C51F9
0x1800c50d4  mov     rax, [r13+268h]
0x1800c50db  cmp     dword ptr [rax+4], 6
0x1800c50df  jnz     loc_1800C51F9
0x1800c50e5  mov     rcx, [r13+3D0h]
0x1800c50ec  test    rcx, rcx
0x1800c50ef  jz      loc_1800C51F9
0x1800c50f5  cmp     dword ptr [rcx+64h], 0
0x1800c50f9  jnz     loc_1800C51F9
0x1800c50ff  test    byte ptr [rcx+144h], 2
0x1800c5106  mov     rax, [rcx+128h]
0x1800c510d  mov     eax, [rax+14h]
0x1800c5110  jnz     short loc_1800C5121
0x1800c5112  mov     ecx, eax; netlong
0x1800c5114  call    cs:__imp_ntohl
0x1800c511a  lea     rdx, WPP_GLOBAL_Control
0x1800c5121  cmp     edi, eax
0x1800c5123  jnz     loc_1800C51F9
0x1800c5129  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c5130  cmp     rdi, rdx
0x1800c5133  jz      short loc_1800C516E
0x1800c5135  cmp     byte ptr [rdi+19h], 4
0x1800c5139  jb      short loc_1800C516E
0x1800c513b  test    byte ptr [rdi+1Ch], 10h
0x1800c513f  jz      short loc_1800C516E
0x1800c5141  mov     rdi, [rdi+10h]
0x1800c5145  call    IkeGetTlsPeerAddr
0x1800c514a  mov     rbx, rax
0x1800c514d  call    IkeGetTlsMmLuid
0x1800c5152  mov     r9, rax
0x1800c5155  mov     [rsp+0F0h+var_D0], rbx
0x1800c515a  mov     edx, 15h
0x1800c515f  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5166  mov     rcx, rdi
0x1800c5169  call    WPP_SF_iS
0x1800c516e  mov     eax, cs:dword_180173278
0x1800c5174  cmp     eax, 4
0x1800c5177  jbe     short loc_1800C51EE
0x1800c5179  call    IkeGetTlsMmLuid
0x1800c517e  mov     [rbp+57h+var_C0], rax
0x1800c5182  lea     rax, [rbp+57h+var_C0]
0x1800c5186  mov     [rbp+57h+var_80], rax
0x1800c518a  mov     [rbp+57h+var_78], 8
0x1800c5192  call    IkeGetTlsPeerAddr
0x1800c5197  mov     rdx, rax
0x1800c519a  lea     rcx, [rbp+57h+var_70]
0x1800c519e  call    _tlgCreate1Sz_wchar_t
0x1800c51a3  lea     rax, [rbp+57h+var_B0]
0x1800c51a7  mov     [rbp+57h+var_58], 20h ; ' '
0x1800c51af  mov     [rbp+57h+var_50], rax
0x1800c51b3  lea     rcx, aSwitchingToInp; "Switching to INPLACE_REKEY path"
0x1800c51ba  lea     rax, [rbp+57h+var_A0]
0x1800c51be  mov     [rbp+57h+var_60], rcx
0x1800c51c2  mov     [rsp+0F0h+var_C8], rax
0x1800c51c7  lea     rdx, dword_18015C084
0x1800c51ce  lea     rcx, dword_180173278
0x1800c51d5  mov     dword ptr [rsp+0F0h+var_D0], 6
0x1800c51dd  mov     [rbp+57h+var_B0], r13
0x1800c51e1  mov     [rbp+57h+var_48], 8
0x1800c51e9  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c51ee  or      dword ptr [rsi+4], 1
0x1800c51f2  mov     dword ptr [rsi+10h], 5
0x1800c51f9  lea     rdx, [rbp+57h+var_B8]
0x1800c51fd  mov     rcx, r12
0x1800c5200  call    IkeCheckForMMSAIkeV2
0x1800c5205  mov     r15, rax
0x1800c5208  test    rax, rax
0x1800c520b  jnz     loc_1800C5331
0x1800c5211  lea     rbx, [rsi+10h]
0x1800c5215  cmp     dword ptr [rbp+57h+var_B8], eax
0x1800c5218  jz      short loc_1800C5220
0x1800c521a  mov     dword ptr [rbx], 5
0x1800c5220  cmp     dword ptr [rsi], 0
0x1800c5223  jz      loc_1800C5321
0x1800c5229  test    byte ptr [r14], 20h
0x1800c522d  jz      loc_1800C5306
0x1800c5233  lea     r14, [rsi+10h]
0x1800c5237  cmp     dword ptr [r14], 5
0x1800c523b  jz      loc_1800C5306
0x1800c5241  mov     rdi, cs:WPP_GLOBAL_Control
0x1800c5248  lea     rax, WPP_GLOBAL_Control
0x1800c524f  cmp     rdi, rax
0x1800c5252  jz      short loc_1800C528D
0x1800c5254  cmp     byte ptr [rdi+19h], 4
0x1800c5258  jb      short loc_1800C528D
0x1800c525a  test    byte ptr [rdi+1Ch], 10h
0x1800c525e  jz      short loc_1800C528D
0x1800c5260  mov     rdi, [rdi+10h]
0x1800c5264  call    IkeGetTlsPeerAddr
0x1800c5269  mov     rbx, rax
0x1800c526c  call    IkeGetTlsMmLuid
0x1800c5271  mov     r9, rax
0x1800c5274  mov     [rsp+0F0h+var_D0], rbx
0x1800c5279  mov     edx, 16h
0x1800c527e  lea     r8, WPP_caf746ea5eb1363761fbc4e0554aaa8f_Traceguids
0x1800c5285  mov     rcx, rdi
0x1800c5288  call    WPP_SF_iS
0x1800c528d  mov     eax, cs:dword_180173278
0x1800c5293  cmp     eax, 4
0x1800c5296  jbe     short loc_1800C52F9
0x1800c5298  call    IkeGetTlsMmLuid
0x1800c529d  mov     [rbp+57h+var_B0], rax
0x1800c52a1  lea     rax, [rbp+57h+var_B0]
0x1800c52a5  mov     [rbp+57h+var_80], rax
0x1800c52a9  mov     [rbp+57h+var_78], 8
0x1800c52b1  call    IkeGetTlsPeerAddr
0x1800c52b6  mov     rdx, rax
0x1800c52b9  lea     rcx, [rbp+57h+var_70]
0x1800c52bd  call    _tlgCreate1Sz_wchar_t
0x1800c52c2  lea     rcx, aReceivedNewQmA; "Received new QM as response. Dropping"
0x1800c52c9  mov     [rbp+57h+var_58], 26h ; '&'
0x1800c52d1  lea     rax, [rbp+57h+var_A0]
0x1800c52d5  mov     [rbp+57h+var_60], rcx
0x1800c52d9  mov     [rsp+0F0h+var_C8], rax
0x1800c52de  lea     rcx, dword_180173278
0x1800c52e5  lea     rdx, qword_18015C008
0x1800c52ec  mov     dword ptr [rsp+0F0h+var_D0], 5
0x1800c52f4  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800c52f9  or      dword ptr [rsi+4], 8
0x1800c52fd  mov     dword ptr [r14], 4
0x1800c5304  jmp     short loc_1800C5324
0x1800c5306  mov     r8, rsi
0x1800c5309  mov     rdx, r12
0x1800c530c  mov     rcx, r13
0x1800c530f  call    IkeIsNewQMSAAllowed
0x1800c5314  mov     r15, rax
0x1800c5317  mov     r14, rbx
0x1800c531a  test    rax, rax
0x1800c531d  jnz     short loc_1800C5331
0x1800c531f  jmp     short loc_1800C5324
0x1800c5321  mov     r14, rbx
0x1800c5324  cmp     dword ptr [r14], 0
0x1800c5328  jnz     short loc_1800C5331
0x1800c532a  mov     dword ptr [r14], 1
0x1800c5331  xor     edx, edx
0x1800c5333  lea     rcx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c533a  call    TraceLogHelper
0x1800c533f  lea     rdx, aIkedetermineqm; "IkeDetermineQMPathIkeV2"
0x1800c5346  mov     rcx, r15
0x1800c5349  call    IkeReturnError
0x1800c534e  mov     rcx, [rbp+57h+var_40]
0x1800c5352  xor     rcx, rsp; StackCookie
0x1800c5355  call    __security_check_cookie
0x1800c535a  mov     rbx, [rsp+0F0h+arg_18]
0x1800c5362  add     rsp, 0C0h
0x1800c5369  pop     r15
0x1800c536b  pop     r14
0x1800c536d  pop     r13
0x1800c536f  pop     r12
0x1800c5371  pop     rdi
0x1800c5372  pop     rsi
0x1800c5373  pop     rbp
0x1800c5374  retn
```
