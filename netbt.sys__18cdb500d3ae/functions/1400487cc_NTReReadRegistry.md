# NTReReadRegistry

- ea: `0x1400487cc`
- end: `0x140048951`
- name: `NTReReadRegistry`
- size: `389`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140027200`
- `0x140047f20`

## callees

- `0x14000e408`
- `0x140017954`
- `0x14001c134`
- `0x140031440`
- `0x140040294`
- `0x140041c38`
- `0x14004256c`
- `0x1400487cc`
- `0x140048ac0`

## pseudocode

```c
__int64 __fastcall NTReReadRegistry(__int64 a1, int a2)
{
  __int64 v4; // rcx
  int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rdx
  _OWORD v9[4]; // [rsp+30h] [rbp-48h] BYREF

  memset(v9, 0, sizeof(v9));
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_Z(1049, 51, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, a1 + 456);
  if ( (unsigned int)LookupDeviceInRegistry((const UNICODE_STRING *)(a1 + 456), v9, 0) )
  {
    if ( (xmmword_140038420 & 8) != 0 )
      WPP_SF_(1027, 53, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids);
  }
  else
  {
    v4 = LOWORD(v9[3]);
    v5 = 0;
    v6 = LOWORD(v9[3]);
    *(_QWORD *)(a1 + 504) = *(_QWORD *)&v9[0];
    *(_WORD *)(a1 + 856) = 0;
    *(_DWORD *)(a1 + 552) = (unsigned __int16)v4;
    if ( (_DWORD)v4 )
    {
      do
      {
        v4 = (unsigned int)v5++;
        *(_DWORD *)(a1 + 4 * v4 + 512) = *((_DWORD *)v9 + v4 + 2);
      }
      while ( v5 < (int)v6 );
    }
    v7 = BYTE4(v9[3]);
    *(_BYTE *)(a1 + 864) = BYTE4(v9[3]);
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      WPP_SF_Zd(1049, 52, (unsigned int)WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids, a1 + 472, v7);
    *(_DWORD *)(a1 + 868) = DWORD2(v9[3]);
    *(_BYTE *)(a1 + 908) = BYTE12(v9[3]);
    SetNodeType(v4, v7, v6);
  }
  if ( *(_DWORD *)(a1 + 488) )
  {
    if ( (NodeType & 1) != 0 )
    {
      NbtStopRefreshTimer();
    }
    else if ( a2 )
    {
      dword_14003962C = 196611;
      ReRegisterLocalNames(a1, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400487cc  mov     [rsp+arg_0], rbx
0x1400487d1  mov     [rsp+arg_8], rsi
0x1400487d6  push    rdi
0x1400487d7  sub     rsp, 70h
0x1400487db  mov     esi, edx
0x1400487dd  mov     rbx, rcx
0x1400487e0  xor     edx, edx; Val
0x1400487e2  lea     rcx, [rsp+78h+var_48]; void *
0x1400487e7  lea     r8d, [rdx+40h]; Size
0x1400487eb  call    memset
0x1400487f0  test    byte ptr cs:xmmword_140038420+3, 2
0x1400487f7  lea     rdi, [rbx+1C8h]
0x1400487fe  jnz     loc_1400488F2
0x140048804  xor     r8d, r8d
0x140048807  lea     rdx, [rsp+78h+var_48]
0x14004880c  mov     rcx, rdi
0x14004880f  call    LookupDeviceInRegistry
0x140048814  xor     edi, edi
0x140048816  test    eax, eax
0x140048818  jnz     loc_1400488B7
0x14004881e  movzx   ecx, [rsp+78h+var_18]
0x140048823  mov     edx, edi
0x140048825  mov     eax, [rsp+78h+var_48]
0x140048829  mov     r8d, ecx
0x14004882c  mov     [rbx+1F8h], eax
0x140048832  mov     eax, [rsp+78h+var_44]
0x140048836  mov     [rbx+1FCh], eax
0x14004883c  mov     [rbx+358h], di
0x140048843  mov     [rbx+228h], cx
0x14004884a  mov     [rbx+22Ah], di
0x140048851  test    ecx, ecx
0x140048853  jnz     loc_140048910
0x140048859  movzx   edx, [rsp+78h+var_14]
0x14004885e  mov     [rbx+360h], dl
0x140048864  test    byte ptr cs:xmmword_140038420+3, 2
0x14004886b  jnz     loc_140048929
0x140048871  mov     eax, [rsp+78h+var_10]
0x140048875  mov     [rbx+364h], eax
0x14004887b  mov     al, [rsp+78h+var_C]
0x14004887f  mov     [rbx+38Ch], al
0x140048885  call    SetNodeType
0x14004888a  cmp     [rbx+1E8h], edi
0x140048890  jnz     short loc_1400488A7
0x140048892  lea     r11, [rsp+78h+var_8]
0x140048897  xor     eax, eax
0x140048899  mov     rbx, [r11+10h]
0x14004889d  mov     rsi, [r11+18h]
0x1400488a1  mov     rsp, r11
0x1400488a4  pop     rdi
0x1400488a5  retn
0x1400488a7  test    byte ptr cs:NodeType, 1
0x1400488ae  jz      short loc_1400488D8
0x1400488b0  call    NbtStopRefreshTimer
0x1400488b5  jmp     short loc_140048892
0x1400488b7  test    byte ptr cs:xmmword_140038420, 8
0x1400488be  jz      short loc_14004888A
0x1400488c0  mov     edx, 35h ; '5'
0x1400488c5  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x1400488cc  mov     ecx, 403h
0x1400488d1  call    WPP_SF_
0x1400488d6  jmp     short loc_14004888A
0x1400488d8  test    esi, esi
0x1400488da  jz      short loc_140048892
0x1400488dc  xor     edx, edx
0x1400488de  mov     cs:dword_14003962C, 30003h
0x1400488e8  mov     rcx, rbx
0x1400488eb  call    ReRegisterLocalNames
0x1400488f0  jmp     short loc_140048892
0x1400488f2  mov     edx, 33h ; '3'
0x1400488f7  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x1400488fe  mov     ecx, 419h
0x140048903  mov     r9, rdi
0x140048906  call    WPP_SF_Z
0x14004890b  jmp     loc_140048804
0x140048910  mov     ecx, edx
0x140048912  inc     edx
0x140048914  mov     eax, [rsp+rcx*4+78h+var_40]
0x140048918  mov     [rbx+rcx*4+200h], eax
0x14004891f  cmp     edx, r8d
0x140048922  jl      short loc_140048910
0x140048924  jmp     loc_140048859
0x140048929  mov     eax, edx
0x14004892b  lea     r9, [rbx+1D8h]
0x140048932  mov     edx, 34h ; '4'
0x140048937  mov     [rsp+78h+var_58], eax
0x14004893b  mov     ecx, 419h
0x140048940  lea     r8, WPP_6fbf3721221234eecc9a3cdb64421ce5_Traceguids
0x140048947  call    WPP_SF_Zd
0x14004894c  jmp     loc_140048871
```
