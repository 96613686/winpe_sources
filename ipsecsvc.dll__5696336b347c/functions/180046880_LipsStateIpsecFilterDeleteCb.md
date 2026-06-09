# LipsStateIpsecFilterDeleteCb

- ea: `0x180046880`
- end: `0x180046a45`
- name: `LipsStateIpsecFilterDeleteCb`
- size: `453`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180046880`
- `0x180047f60`

## string_xrefs

- `0x180046a28`: `LipsStateIpsecFilterDeleteCb`

## pseudocode

```c
__int64 __fastcall LipsStateIpsecFilterDeleteCb(__int64 a1)
{
  unsigned int v1; // ebx
  GUID ***v2; // rdi
  GUID **v3; // rax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  GUID *v6; // rcx
  GUID *v7; // rcx
  GUID *v8; // rcx
  GUID *v9; // rcx
  GUID *v10; // rcx

  v1 = 0;
  v2 = (GUID ***)(a1 + 200);
  if ( a1 != -200 )
  {
    v3 = *v2;
    if ( *v2 )
    {
      if ( *v3 )
      {
        v1 = LipsBfeFilterDelete(*v3);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 35;
LABEL_33:
          WPP_SF_d(v4[2], v5, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v1);
          return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
        }
      }
      v6 = (*v2)[3];
      if ( v6 )
      {
        v1 = LipsBfeFilterDelete(v6);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 36;
          goto LABEL_33;
        }
      }
      v7 = (*v2)[4];
      if ( v7 )
      {
        v1 = LipsBfeFilterDelete(v7);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 37;
          goto LABEL_33;
        }
      }
      v8 = (*v2)[5];
      if ( v8 )
      {
        v1 = LipsBfeFilterDelete(v8);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 38;
          goto LABEL_33;
        }
      }
      v9 = (*v2)[6];
      if ( v9 )
      {
        v1 = LipsBfeFilterDelete(v9);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 39;
          goto LABEL_33;
        }
      }
      v10 = (*v2)[7];
      if ( v10 )
      {
        v1 = LipsBfeFilterDelete(v10);
        if ( v1 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v1, (int)"LipsStateIpsecFilterDeleteCb");
          }
          v5 = 40;
          goto LABEL_33;
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180046880  mov     [rsp+arg_0], rbx
0x180046885  push    rdi
0x180046886  sub     rsp, 20h
0x18004688a  xor     ebx, ebx
0x18004688c  lea     rdi, [rcx+0C8h]
0x180046893  test    rdi, rdi
0x180046896  jz      loc_180046A38
0x18004689c  mov     rax, [rdi]
0x18004689f  test    rax, rax
0x1800468a2  jz      loc_180046A38
0x1800468a8  mov     rcx, [rax]; key
0x1800468ab  test    rcx, rcx
0x1800468ae  jz      short loc_1800468E6
0x1800468b0  call    LipsBfeFilterDelete
0x1800468b5  mov     ebx, eax
0x1800468b7  test    eax, eax
0x1800468b9  jz      short loc_1800468E6
0x1800468bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468c2  lea     rax, WPP_GLOBAL_Control
0x1800468c9  cmp     rcx, rax
0x1800468cc  jz      loc_180046A28
0x1800468d2  test    byte ptr [rcx+1Ch], 10h
0x1800468d6  jz      loc_180046A28
0x1800468dc  mov     edx, 23h ; '#'
0x1800468e1  jmp     loc_180046A15
0x1800468e6  mov     rax, [rdi]
0x1800468e9  mov     rcx, [rax+18h]; key
0x1800468ed  test    rcx, rcx
0x1800468f0  jz      short loc_180046928
0x1800468f2  call    LipsBfeFilterDelete
0x1800468f7  mov     ebx, eax
0x1800468f9  test    eax, eax
0x1800468fb  jz      short loc_180046928
0x1800468fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180046904  lea     rax, WPP_GLOBAL_Control
0x18004690b  cmp     rcx, rax
0x18004690e  jz      loc_180046A28
0x180046914  test    byte ptr [rcx+1Ch], 10h
0x180046918  jz      loc_180046A28
0x18004691e  mov     edx, 24h ; '$'
0x180046923  jmp     loc_180046A15
0x180046928  mov     rax, [rdi]
0x18004692b  mov     rcx, [rax+20h]; key
0x18004692f  test    rcx, rcx
0x180046932  jz      short loc_18004696A
0x180046934  call    LipsBfeFilterDelete
0x180046939  mov     ebx, eax
0x18004693b  test    eax, eax
0x18004693d  jz      short loc_18004696A
0x18004693f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046946  lea     rax, WPP_GLOBAL_Control
0x18004694d  cmp     rcx, rax
0x180046950  jz      loc_180046A28
0x180046956  test    byte ptr [rcx+1Ch], 10h
0x18004695a  jz      loc_180046A28
0x180046960  mov     edx, 25h ; '%'
0x180046965  jmp     loc_180046A15
0x18004696a  mov     rax, [rdi]
0x18004696d  mov     rcx, [rax+28h]; key
0x180046971  test    rcx, rcx
0x180046974  jz      short loc_1800469A9
0x180046976  call    LipsBfeFilterDelete
0x18004697b  mov     ebx, eax
0x18004697d  test    eax, eax
0x18004697f  jz      short loc_1800469A9
0x180046981  mov     rcx, cs:WPP_GLOBAL_Control
0x180046988  lea     rax, WPP_GLOBAL_Control
0x18004698f  cmp     rcx, rax
0x180046992  jz      loc_180046A28
0x180046998  test    byte ptr [rcx+1Ch], 10h
0x18004699c  jz      loc_180046A28
0x1800469a2  mov     edx, 26h ; '&'
0x1800469a7  jmp     short loc_180046A15
0x1800469a9  mov     rax, [rdi]
0x1800469ac  mov     rcx, [rax+30h]; key
0x1800469b0  test    rcx, rcx
0x1800469b3  jz      short loc_1800469E0
0x1800469b5  call    LipsBfeFilterDelete
0x1800469ba  mov     ebx, eax
0x1800469bc  test    eax, eax
0x1800469be  jz      short loc_1800469E0
0x1800469c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469c7  lea     rax, WPP_GLOBAL_Control
0x1800469ce  cmp     rcx, rax
0x1800469d1  jz      short loc_180046A28
0x1800469d3  test    byte ptr [rcx+1Ch], 10h
0x1800469d7  jz      short loc_180046A28
0x1800469d9  mov     edx, 27h ; '''
0x1800469de  jmp     short loc_180046A15
0x1800469e0  mov     rax, [rdi]
0x1800469e3  mov     rcx, [rax+38h]; key
0x1800469e7  test    rcx, rcx
0x1800469ea  jz      short loc_180046A38
0x1800469ec  call    LipsBfeFilterDelete
0x1800469f1  mov     ebx, eax
0x1800469f3  test    eax, eax
0x1800469f5  jz      short loc_180046A38
0x1800469f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469fe  lea     rax, WPP_GLOBAL_Control
0x180046a05  cmp     rcx, rax
0x180046a08  jz      short loc_180046A28
0x180046a0a  test    byte ptr [rcx+1Ch], 10h
0x180046a0e  jz      short loc_180046A28
0x180046a10  mov     edx, 28h ; '('
0x180046a15  mov     rcx, [rcx+10h]
0x180046a19  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046a20  mov     r9d, ebx
0x180046a23  call    WPP_SF_d
0x180046a28  lea     rdx, aLipsstateipsec_5; "LipsStateIpsecFilterDeleteCb"
0x180046a2f  mov     ecx, ebx
0x180046a31  call    LipsReportError
0x180046a36  mov     ebx, eax
0x180046a38  mov     eax, ebx
0x180046a3a  mov     rbx, [rsp+28h+arg_0]
0x180046a3f  add     rsp, 20h
0x180046a43  pop     rdi
0x180046a44  retn
```
