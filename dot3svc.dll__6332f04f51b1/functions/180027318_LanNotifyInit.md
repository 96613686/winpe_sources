# LanNotifyInit

- ea: `0x180027318`
- end: `0x180027677`
- name: `LanNotifyInit`
- size: `863`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000aac0`

## callees

- `0x180003114`
- `0x18000a9c0`
- `0x18000c230`
- `0x180014d14`
- `0x18001e140`
- `0x180027318`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027463`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800274c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027513`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027565`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027463`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800274c4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027513`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800274d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027525`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027577`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800273d0`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800273d0`
- `DSROLE!DsRoleFreeMemory` at `0x180027637`
- `DSROLE!DsRoleFreeMemory` at `0x180027637`
- `SYSNTFY!SysNotifyStartServer` at `0x1800275ec`
- `SYSNTFY!SysNotifyStartServer` at `0x1800275ec`

## pseudocode

```c
__int64 LanNotifyInit()
{
  struct _LIST_ENTRY *v0; // rcx
  unsigned int v1; // ebx
  DWORD PrimaryDomainInformation; // eax
  DWORD started; // eax
  __int64 v4; // rdx
  _DWORD v6[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int64 (__fastcall *v7)(); // [rsp+50h] [rbp-88h]
  __int64 (__fastcall *v8)(); // [rsp+88h] [rbp-50h]
  PBYTE Buffer; // [rsp+E0h] [rbp+8h] BYREF

  memset_0(v6, 0, 0x80u);
  Buffer = 0;
  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( dword_180052FCC )
  {
    v1 = 1247;
    if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) && (BYTE4(v0[1].Blink) & 1) != 0 )
    {
      WPP_SF_(v0[1].Flink, 15, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids);
LABEL_44:
      v0 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    PrimaryDomainInformation = DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer);
    v1 = PrimaryDomainInformation;
    if ( !PrimaryDomainInformation )
    {
      g_bDomainJoined = (*(_DWORD *)Buffer & 0xFFFFFFFD) != 0;
      StSetTimelyKey(0);
      hObject = CreateEventW(0, 1, 0, 0);
      if ( hObject )
      {
        hHandle = CreateEventW(0, 1, 0, 0);
        if ( hHandle )
        {
          qword_180052FB8 = CreateEventW(0, 1, 0, 0);
          if ( qword_180052FB8 )
          {
            hEvent = CreateEventW(0, 1, 0, 0);
            if ( hEvent )
            {
              v6[0] = 1;
              v7 = LanNotifyOnLogon;
              v8 = LanNotifyOnLogoff;
              started = SysNotifyStartServer("Dot3svc", 128, v6, 0, &qword_180052FD0);
              v1 = started;
              if ( !started )
              {
                dword_180052FCC = 1;
                goto LABEL_44;
              }
              v0 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control[1].Blink)
                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              {
                goto LABEL_45;
              }
              v4 = 21;
            }
            else
            {
              started = GetLastError();
              v1 = started;
              v0 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                || !BYTE1(WPP_GLOBAL_Control[1].Blink)
                || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              {
                goto LABEL_45;
              }
              v4 = 20;
            }
          }
          else
          {
            started = GetLastError();
            v1 = started;
            v0 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || !BYTE1(WPP_GLOBAL_Control[1].Blink)
              || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            {
              goto LABEL_45;
            }
            v4 = 19;
          }
        }
        else
        {
          started = GetLastError();
          v1 = started;
          v0 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_45;
          }
          v4 = 18;
        }
      }
      else
      {
        started = GetLastError();
        v1 = started;
        v0 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_45;
        }
        v4 = 17;
      }
      WPP_SF_d(v0[1].Flink, v4, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids, started);
      goto LABEL_44;
    }
    v0 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        16,
        WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids,
        PrimaryDomainInformation);
      v0 = WPP_GLOBAL_Control;
    }
    if ( (Microsoft_Windows_Wired_AutoConfigEnableBits & 4) != 0 )
    {
      McTemplateU0qqq_EtwEventWriteTransfer(v0, LNI_GetPrimaryDomainInfoFailed, v1, 91);
      goto LABEL_44;
    }
  }
LABEL_45:
  if ( Buffer )
  {
    DsRoleFreeMemory(Buffer);
    v0 = WPP_GLOBAL_Control;
  }
  if ( v0 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v0[1].Blink) >= 4u && (BYTE4(v0[1].Blink) & 1) != 0 )
    WPP_SF_d(v0[1].Flink, 22, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x180027318  push    rbx
0x18002731a  push    rbp
0x18002731b  push    rsi
0x18002731c  push    rdi
0x18002731d  sub     rsp, 0B8h
0x180027324  xor     edx, edx; Val
0x180027326  lea     rcx, [rsp+0D8h+var_A8]; void *
0x18002732b  mov     r8d, 80h; Size
0x180027331  call    memset_0
0x180027336  mov     [rsp+0D8h+Buffer], 0
0x180027342  mov     rcx, cs:WPP_GLOBAL_Control
0x180027349  lea     rsi, WPP_GLOBAL_Control
0x180027350  lea     rbp, WPP_d4bbd877e36935dbcf9c3e0cbedae6f2_Traceguids
0x180027357  mov     edi, 1
0x18002735c  cmp     rcx, rsi
0x18002735f  jz      short loc_180027383
0x180027361  cmp     byte ptr [rcx+19h], 4
0x180027365  jb      short loc_180027383
0x180027367  test    [rcx+1Ch], dil
0x18002736b  jz      short loc_180027383
0x18002736d  mov     rcx, [rcx+10h]
0x180027371  lea     edx, [rdi+0Dh]
0x180027374  mov     r8, rbp
0x180027377  call    WPP_SF_
0x18002737c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027383  cmp     cs:dword_180052FCC, 0
0x18002738a  jz      short loc_1800273C4
0x18002738c  mov     ebx, 4DFh
0x180027391  cmp     rcx, rsi
0x180027394  jz      loc_180027627
0x18002739a  cmp     [rcx+19h], dil
0x18002739e  jb      loc_180027627
0x1800273a4  test    [rcx+1Ch], dil
0x1800273a8  jz      loc_180027627
0x1800273ae  mov     rcx, [rcx+10h]
0x1800273b2  mov     edx, 0Fh
0x1800273b7  mov     r8, rbp
0x1800273ba  call    WPP_SF_
0x1800273bf  jmp     loc_180027620
0x1800273c4  lea     r8, [rsp+0D8h+Buffer]; Buffer
0x1800273cc  mov     edx, edi; InfoLevel
0x1800273ce  xor     ecx, ecx; lpServer
0x1800273d0  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800273d6  mov     ebx, eax
0x1800273d8  test    eax, eax
0x1800273da  jz      short loc_180027436
0x1800273dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273e3  cmp     rcx, rsi
0x1800273e6  jz      short loc_18002740F
0x1800273e8  cmp     [rcx+19h], dil
0x1800273ec  jb      short loc_18002740F
0x1800273ee  test    [rcx+1Ch], dil
0x1800273f2  jz      short loc_18002740F
0x1800273f4  mov     rcx, [rcx+10h]
0x1800273f8  mov     edx, 10h
0x1800273fd  mov     r9d, eax
0x180027400  mov     r8, rbp
0x180027403  call    WPP_SF_d
0x180027408  mov     rcx, cs:WPP_GLOBAL_Control
0x18002740f  test    cs:Microsoft_Windows_Wired_AutoConfigEnableBits, 4
0x180027416  jz      loc_180027627
0x18002741c  mov     r9d, 5Bh ; '['
0x180027422  lea     rdx, LNI_GetPrimaryDomainInfoFailed
0x180027429  mov     r8d, ebx
0x18002742c  call    McTemplateU0qqq_EtwEventWriteTransfer
0x180027431  jmp     loc_180027620
0x180027436  mov     rax, [rsp+0D8h+Buffer]
0x18002743e  test    dword ptr [rax], 0FFFFFFFDh
0x180027444  mov     eax, 0
0x180027449  setnz   al
0x18002744c  xor     ecx, ecx; int
0x18002744e  mov     cs:g_bDomainJoined, eax
0x180027454  call    ?StSetTimelyKey@@YAKHH@Z; StSetTimelyKey(int,int)
0x180027459  xor     r9d, r9d; lpName
0x18002745c  xor     r8d, r8d; bInitialState
0x18002745f  mov     edx, edi; bManualReset
0x180027461  xor     ecx, ecx; lpEventAttributes
0x180027463  call    cs:__imp_CreateEventW
0x180027469  mov     cs:hObject, rax
0x180027470  test    rax, rax
0x180027473  jnz     short loc_1800274BA
0x180027475  call    cs:__imp_GetLastError
0x18002747b  mov     ebx, eax
0x18002747d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027484  cmp     rcx, rsi
0x180027487  jz      loc_180027627
0x18002748d  cmp     [rcx+19h], dil
0x180027491  jb      loc_180027627
0x180027497  test    [rcx+1Ch], dil
0x18002749b  jz      loc_180027627
0x1800274a1  mov     edx, 11h
0x1800274a6  mov     rcx, [rcx+10h]
0x1800274aa  mov     r9d, eax
0x1800274ad  mov     r8, rbp
0x1800274b0  call    WPP_SF_d
0x1800274b5  jmp     loc_180027620
0x1800274ba  xor     r9d, r9d; lpName
0x1800274bd  xor     r8d, r8d; bInitialState
0x1800274c0  mov     edx, edi; bManualReset
0x1800274c2  xor     ecx, ecx; lpEventAttributes
0x1800274c4  call    cs:__imp_CreateEventW
0x1800274ca  mov     cs:hHandle, rax
0x1800274d1  test    rax, rax
0x1800274d4  jnz     short loc_180027509
0x1800274d6  call    cs:__imp_GetLastError
0x1800274dc  mov     ebx, eax
0x1800274de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274e5  cmp     rcx, rsi
0x1800274e8  jz      loc_180027627
0x1800274ee  cmp     [rcx+19h], dil
0x1800274f2  jb      loc_180027627
0x1800274f8  test    [rcx+1Ch], dil
0x1800274fc  jz      loc_180027627
0x180027502  mov     edx, 12h
0x180027507  jmp     short loc_1800274A6
0x180027509  xor     r9d, r9d; lpName
0x18002750c  xor     r8d, r8d; bInitialState
0x18002750f  mov     edx, edi; bManualReset
0x180027511  xor     ecx, ecx; lpEventAttributes
0x180027513  call    cs:__imp_CreateEventW
0x180027519  mov     cs:qword_180052FB8, rax
0x180027520  test    rax, rax
0x180027523  jnz     short loc_18002755B
0x180027525  call    cs:__imp_GetLastError
0x18002752b  mov     ebx, eax
0x18002752d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027534  cmp     rcx, rsi
0x180027537  jz      loc_180027627
0x18002753d  cmp     [rcx+19h], dil
0x180027541  jb      loc_180027627
0x180027547  test    [rcx+1Ch], dil
0x18002754b  jz      loc_180027627
0x180027551  mov     edx, 13h
0x180027556  jmp     loc_1800274A6
0x18002755b  xor     r9d, r9d; lpName
0x18002755e  xor     r8d, r8d; bInitialState
0x180027561  mov     edx, edi; bManualReset
0x180027563  xor     ecx, ecx; lpEventAttributes
0x180027565  call    cs:__imp_CreateEventW
0x18002756b  mov     cs:hEvent, rax
0x180027572  test    rax, rax
0x180027575  jnz     short loc_1800275AD
0x180027577  call    cs:__imp_GetLastError
0x18002757d  mov     ebx, eax
0x18002757f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027586  cmp     rcx, rsi
0x180027589  jz      loc_180027627
0x18002758f  cmp     [rcx+19h], dil
0x180027593  jb      loc_180027627
0x180027599  test    [rcx+1Ch], dil
0x18002759d  jz      loc_180027627
0x1800275a3  mov     edx, 14h
0x1800275a8  jmp     loc_1800274A6
0x1800275ad  lea     rax, LanNotifyOnLogon
0x1800275b4  mov     [rsp+0D8h+var_A8], edi
0x1800275b8  mov     [rsp+0D8h+var_88], rax
0x1800275bd  lea     r8, [rsp+0D8h+var_A8]
0x1800275c2  lea     rax, LanNotifyOnLogoff
0x1800275c9  xor     r9d, r9d
0x1800275cc  mov     [rsp+0D8h+var_50], rax
0x1800275d4  lea     rcx, aDot3svc; "Dot3svc"
0x1800275db  lea     rax, qword_180052FD0
0x1800275e2  mov     edx, 80h
0x1800275e7  mov     [rsp+0D8h+var_B8], rax
0x1800275ec  call    cs:__imp_SysNotifyStartServer
0x1800275f2  mov     ebx, eax
0x1800275f4  test    eax, eax
0x1800275f6  jz      short loc_18002761A
0x1800275f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275ff  cmp     rcx, rsi
0x180027602  jz      short loc_180027627
0x180027604  cmp     [rcx+19h], dil
0x180027608  jb      short loc_180027627
0x18002760a  test    [rcx+1Ch], dil
0x18002760e  jz      short loc_180027627
0x180027610  mov     edx, 15h
0x180027615  jmp     loc_1800274A6
0x18002761a  mov     cs:dword_180052FCC, edi
0x180027620  mov     rcx, cs:WPP_GLOBAL_Control
0x180027627  mov     rax, [rsp+0D8h+Buffer]
0x18002762f  test    rax, rax
0x180027632  jz      short loc_180027644
0x180027634  mov     rcx, rax; Buffer
0x180027637  call    cs:__imp_DsRoleFreeMemory
0x18002763d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027644  cmp     rcx, rsi
0x180027647  jz      short loc_180027669
0x180027649  cmp     byte ptr [rcx+19h], 4
0x18002764d  jb      short loc_180027669
0x18002764f  test    [rcx+1Ch], dil
0x180027653  jz      short loc_180027669
0x180027655  mov     rcx, [rcx+10h]
0x180027659  mov     edx, 16h
0x18002765e  mov     r9d, ebx
0x180027661  mov     r8, rbp
0x180027664  call    WPP_SF_d
0x180027669  mov     eax, ebx
0x18002766b  add     rsp, 0B8h
0x180027672  pop     rdi
0x180027673  pop     rsi
0x180027674  pop     rbp
0x180027675  pop     rbx
0x180027676  retn
```
