# Smb2LkmdTelCollectParsingFailure

- ea: `0x140028000`
- end: `0x14002817d`
- name: `Smb2LkmdTelCollectParsingFailure`
- size: `381`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001ef70`
- `0x1400230b0`
- `0x140024f20`
- `0x140027fc0`

## callees

- `0x140028000`
- `0x140029764`
- `0x14002a9ac`
- `0x140036410`
- `0x140036458`
- `0x140036548`
- `0x140054b60`
- `0x140054b94`
- `0x140054e28`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140028017`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140028038`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140028017`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140028038`

## pseudocode

```c
__int64 __fastcall Smb2LkmdTelCollectParsingFailure(__int64 a1, unsigned int a2, unsigned int a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  wchar_t *Report; // rax
  wchar_t *v11; // rbp
  int v12; // eax
  _DWORD *ParsingFailureThrottlingSlot; // r9
  int v14; // r8d
  __int128 v15; // [rsp+30h] [rbp-18h] BYREF

  result = MRxSmbGetConfigurationBlock(a1);
  if ( *(_BYTE *)(result + 450) )
  {
    v15 = 0;
    result = MRxSmbGetConfigurationBlock(v7);
    if ( *(_BYTE *)(result + 450) )
    {
      result = Smb2IsCollectParsingFailureDiagThrottled(a2, a3);
      if ( !(_BYTE)result )
      {
        Report = LkmdTelCreateReport(v9, v8, (__int64)&v15);
        *(_QWORD *)&v15 = a1;
        v11 = Report;
        *((_QWORD *)&v15 + 1) = __PAIR64__(a2, a3);
        if ( Report )
        {
          Smb2LkmdTelCollectFailureHelper(Report, &v15);
          v12 = LkmdTelSubmitReport(v11);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                12,
                WPP_d7115421331136bc7b15d26dd3bd3577_Traceguids,
                (unsigned int)v12);
            }
          }
          else
          {
            ParsingFailureThrottlingSlot = (_DWORD *)Smb2GetParsingFailureThrottlingSlot(
                                                       a2,
                                                       a3,
                                                       MEMORY[0xFFFFF78000000008],
                                                       (unsigned int)v12);
            *ParsingFailureThrottlingSlot = v14 / 10000000 + v14 + 3600;
          }
          return LkmdTelCloseHandle(v11);
        }
        else
        {
          result = (__int64)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d7115421331136bc7b15d26dd3bd3577_Traceguids);
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140028000  mov     [rsp+arg_8], rbx
0x140028005  mov     [rsp+arg_10], rsi
0x14002800a  push    rdi
0x14002800b  sub     rsp, 40h
0x14002800f  mov     edi, r8d
0x140028012  mov     ebx, edx
0x140028014  mov     rsi, rcx
0x140028017  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002801e  nop     dword ptr [rax+rax+00h]
0x140028023  cmp     byte ptr [rax+1C2h], 0
0x14002802a  jz      loc_14002816C
0x140028030  xorps   xmm0, xmm0
0x140028033  movups  [rsp+48h+var_18], xmm0
0x140028038  call    cs:__imp_MRxSmbGetConfigurationBlock
0x14002803f  nop     dword ptr [rax+rax+00h]
0x140028044  cmp     byte ptr [rax+1C2h], 0
0x14002804b  jz      loc_14002816C
0x140028051  mov     edx, edi
0x140028053  mov     ecx, ebx
0x140028055  call    Smb2IsCollectParsingFailureDiagThrottled
0x14002805a  test    al, al
0x14002805c  jnz     loc_14002816C
0x140028062  lea     r8, [rsp+48h+var_18]
0x140028067  mov     [rsp+48h+arg_0], rbp
0x14002806c  call    LkmdTelCreateReport
0x140028071  mov     qword ptr [rsp+48h+var_18], rsi
0x140028076  mov     rbp, rax
0x140028079  mov     dword ptr [rsp+48h+var_18+8], edi
0x14002807d  mov     dword ptr [rsp+48h+var_18+0Ch], ebx
0x140028081  test    rax, rax
0x140028084  jnz     short loc_1400280CC
0x140028086  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002808d  lea     rax, WPP_GLOBAL_Control
0x140028094  cmp     rcx, rax
0x140028097  jz      loc_140028167
0x14002809d  mov     eax, [rcx+2Ch]
0x1400280a0  test    al, 1
0x1400280a2  jz      loc_140028167
0x1400280a8  cmp     byte ptr [rcx+29h], 4
0x1400280ac  jb      loc_140028167
0x1400280b2  mov     rcx, [rcx+18h]
0x1400280b6  lea     r8, WPP_d7115421331136bc7b15d26dd3bd3577_Traceguids
0x1400280bd  mov     edx, 0Bh
0x1400280c2  call    WPP_SF_
0x1400280c7  jmp     loc_140028167
0x1400280cc  lea     rdx, [rsp+48h+var_18]
0x1400280d1  mov     rcx, rbp
0x1400280d4  call    Smb2LkmdTelCollectFailureHelper
0x1400280d9  mov     rcx, rbp
0x1400280dc  call    LkmdTelSubmitReport
0x1400280e1  mov     r9d, eax
0x1400280e4  test    eax, eax
0x1400280e6  js      short loc_14002812A
0x1400280e8  mov     r8, 0FFFFF78000000008h
0x1400280f2  mov     edx, edi
0x1400280f4  mov     ecx, ebx
0x1400280f6  mov     r8, [r8]
0x1400280f9  call    Smb2GetParsingFailureThrottlingSlot
0x1400280fe  mov     r9, rax
0x140028101  mov     rax, 0D6BF94D5E57A42BDh
0x14002810b  imul    r8
0x14002810e  add     rdx, r8
0x140028111  sar     rdx, 17h
0x140028115  mov     rcx, rdx
0x140028118  shr     rcx, 3Fh
0x14002811c  add     rdx, rcx
0x14002811f  add     edx, 0E10h
0x140028125  mov     [r9], edx
0x140028128  jmp     short loc_14002815F
0x14002812a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028131  lea     rax, WPP_GLOBAL_Control
0x140028138  cmp     rcx, rax
0x14002813b  jz      short loc_14002815F
0x14002813d  mov     eax, [rcx+2Ch]
0x140028140  test    al, 1
0x140028142  jz      short loc_14002815F
0x140028144  cmp     byte ptr [rcx+29h], 4
0x140028148  jb      short loc_14002815F
0x14002814a  mov     rcx, [rcx+18h]
0x14002814e  lea     r8, WPP_d7115421331136bc7b15d26dd3bd3577_Traceguids
0x140028155  mov     edx, 0Ch
0x14002815a  call    WPP_SF_d
0x14002815f  mov     rcx, rbp
0x140028162  call    LkmdTelCloseHandle
0x140028167  mov     rbp, [rsp+48h+arg_0]
0x14002816c  mov     rbx, [rsp+48h+arg_8]
0x140028171  mov     rsi, [rsp+48h+arg_10]
0x140028176  add     rsp, 40h
0x14002817a  pop     rdi
0x14002817b  retn
```
