# AllCollectionPDOsInitialized

- ea: `0x180020038`
- end: `0x180020282`
- name: `AllCollectionPDOsInitialized`
- size: `586`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003e5b0`
- `0x180042f24`

## callees

- `0x18000ddc8`
- `0x18001c8a0`
- `0x180020038`
- `0x180022900`
- `0x180023338`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18002005b`
- `ntoskrnl!MmBadPointer` at `0x18002009d`

## string_xrefs

- `0x1800201ae`: `Unexpected/invalid PDO extension`

## pseudocode

```c
char __fastcall AllCollectionPDOsInitialized(__int64 a1)
{
  int *v1; // rdx
  char v3; // r14
  int v4; // edi
  __int64 v5; // r9
  PVOID v6; // r8
  char v7; // r11
  PDEVICE_OBJECT v8; // rcx
  char v9; // r10
  int v10; // eax
  int v12; // [rsp+20h] [rbp-88h]
  int v13; // [rsp+28h] [rbp-80h]
  int v14; // [rsp+30h] [rbp-78h]
  int v15; // [rsp+38h] [rbp-70h]
  int v16; // [rsp+58h] [rbp-50h]

  v1 = *(int **)(a1 + 272);
  if ( v1 && v1 != MmBadPointer )
  {
    v3 = 1;
    if ( !*v1 )
      return v3;
    v4 = 0;
    while ( 1 )
    {
      v5 = *(_QWORD *)&v1[2 * v4 + 2];
      v6 = (PVOID)(*(_QWORD *)(v5 + 64) + 32LL);
      if ( *(_QWORD *)(v5 + 64) == -32 || v6 == MmBadPointer )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || (v9 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        {
          v9 = 0;
        }
        if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v10 = *v1;
          LOBYTE(v1) = v9;
          LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_qqDD(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v1,
            (_DWORD)v6,
            *(_QWORD *)(a1 + 672),
            v12,
            v13,
            42,
            v15,
            *(_QWORD *)a1,
            v5,
            v10,
            v4);
        }
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v8,
          (unsigned int)(unsigned __int16)v4 | (**(_DWORD **)(a1 + 272) << 16),
          *(unsigned __int16 *)(a1 + 110) | (*(unsigned __int16 *)(a1 + 108) << 16),
          "Unexpected/invalid PDO extension");
      }
      else if ( *(_DWORD *)(*(_QWORD *)(v5 + 64) + 36LL) == 1 )
      {
        v3 = 0;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
          || (v7 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
        {
          v7 = 0;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          || (LOBYTE(v1) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v1) = 0;
        }
        if ( v7 || (_BYTE)v1 )
        {
          LOBYTE(v6) = (_BYTE)v1;
          LOBYTE(v1) = v7;
          WPP_RECORDER_AND_TRACE_SF_qdqDDL(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v1,
            (_DWORD)v6,
            *(_QWORD *)(a1 + 672),
            v12,
            v13,
            v14,
            v15,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 64) + 96LL) + 32LL),
            *(_DWORD *)(*(_QWORD *)(v5 + 64) + 40LL),
            *(_QWORD *)(*(_QWORD *)(v5 + 64) + 80LL),
            v16,
            *(_DWORD *)(*(_QWORD *)(v5 + 64) + 40LL),
            1);
        }
        return v3;
      }
      v1 = *(int **)(a1 + 272);
      if ( ++v4 >= (unsigned int)*v1 )
        return v3;
    }
  }
  v3 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || (LOBYTE(v1) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v1) = 0;
  }
  if ( (_BYTE)v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *(_QWORD *)(a1 + 672),
      4,
      2,
      41,
      (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
      *(_QWORD *)a1,
      1);
  return v3;
}

```

## disassembly

```asm
0x180020038  push    rbx
0x18002003a  push    rbp
0x18002003b  push    rsi
0x18002003c  push    rdi
0x18002003d  push    r14
0x18002003f  push    r15
0x180020041  sub     rsp, 78h
0x180020045  mov     rdx, [rcx+110h]
0x18002004c  xor     r15d, r15d
0x18002004f  mov     rbx, rcx
0x180020052  test    rdx, rdx
0x180020055  jz      loc_1800201ED
0x18002005b  mov     rax, cs:MmBadPointer
0x180020062  cmp     rdx, [rax]
0x180020065  jz      loc_1800201ED
0x18002006b  mov     r14b, 1
0x18002006e  cmp     [rdx], r15d
0x180020071  jbe     loc_180020271
0x180020077  mov     edi, r15d
0x18002007a  lea     rsi, WPP_GLOBAL_Control
0x180020081  lea     rbp, WPP_RECORDER_INITIALIZED
0x180020088  mov     eax, edi
0x18002008a  mov     r9, [rdx+rax*8+8]
0x18002008f  mov     r8, [r9+40h]
0x180020093  add     r8, 20h ; ' '
0x180020097  jz      loc_180020143
0x18002009d  mov     rax, cs:MmBadPointer
0x1800200a4  cmp     r8, [rax]
0x1800200a7  jz      loc_180020143
0x1800200ad  cmp     dword ptr [r8+4], 1
0x1800200b2  jnz     loc_1800201D7
0x1800200b8  mov     r14b, r15b
0x1800200bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200c2  cmp     rcx, rsi
0x1800200c5  jz      short loc_1800200D7
0x1800200c7  mov     eax, [rcx+2Ch]
0x1800200ca  test    al, 2
0x1800200cc  jz      short loc_1800200D7
0x1800200ce  cmp     byte ptr [rcx+29h], 5
0x1800200d2  mov     r11b, 1
0x1800200d5  jnb     short loc_1800200DA
0x1800200d7  mov     r11b, r15b
0x1800200da  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x1800200e1  jz      short loc_1800200EC
0x1800200e3  mov     dl, 1
0x1800200e5  cmp     [rcx+48h], r15w
0x1800200ea  jnz     short loc_1800200EF
0x1800200ec  mov     dl, r15b
0x1800200ef  test    r11b, r11b
0x1800200f2  jnz     short loc_1800200FC
0x1800200f4  test    dl, dl
0x1800200f6  jz      loc_180020271
0x1800200fc  mov     r9d, [r8+8]
0x180020100  mov     rax, [r8+30h]
0x180020104  mov     r10, [r8+40h]
0x180020108  mov     r8b, dl
0x18002010b  mov     rcx, [rcx+18h]
0x18002010f  mov     dl, r11b
0x180020112  mov     [rsp+0A8h+var_40], 1
0x18002011a  mov     [rsp+0A8h+var_48], r9d
0x18002011f  mov     [rsp+0A8h+var_58], rax
0x180020124  mov     rax, [r10+20h]
0x180020128  mov     dword ptr [rsp+0A8h+var_60], r9d
0x18002012d  mov     r9, [rbx+2A0h]
0x180020134  mov     [rsp+0A8h+var_68], rax
0x180020139  call    WPP_RECORDER_AND_TRACE_SF_qdqDDL
0x18002013e  jmp     loc_180020271
0x180020143  mov     rcx, cs:WPP_GLOBAL_Control
0x18002014a  cmp     rcx, rsi
0x18002014d  jz      short loc_180020161
0x18002014f  test    dword ptr [rcx+2Ch], 100h
0x180020156  jz      short loc_180020161
0x180020158  cmp     byte ptr [rcx+29h], 2
0x18002015c  mov     r10b, r14b
0x18002015f  jnb     short loc_180020164
0x180020161  mov     r10b, r15b
0x180020164  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18002016b  setnz   r8b
0x18002016f  test    r10b, r10b
0x180020172  jnz     short loc_180020179
0x180020174  test    r8b, r8b
0x180020177  jz      short loc_1800201AA
0x180020179  mov     eax, [rdx]
0x18002017b  mov     dl, r10b
0x18002017e  mov     rcx, [rcx+18h]
0x180020182  mov     [rsp+0A8h+var_50], edi
0x180020186  mov     dword ptr [rsp+0A8h+var_58], eax
0x18002018a  mov     rax, [rbx]
0x18002018d  mov     [rsp+0A8h+var_60], r9
0x180020192  mov     r9, [rbx+2A0h]
0x180020199  mov     [rsp+0A8h+var_68], rax
0x18002019e  mov     [rsp+0A8h+var_78], 2Ah ; '*'
0x1800201a5  call    WPP_RECORDER_AND_TRACE_SF_qqDD
0x1800201aa  movzx   eax, word ptr [rbx+6Eh]; __annotation("Debug", "TelemetryAssert", "FALSE", "Unexpected/invalid PDO extension")
0x1800201ae  lea     r9, aUnexpectedInva; "Unexpected/invalid PDO extension"
0x1800201b5  movzx   r8d, word ptr [rbx+6Ch]
0x1800201ba  shl     r8d, 10h
0x1800201be  or      r8d, eax
0x1800201c1  mov     rax, [rbx+110h]
0x1800201c8  mov     edx, [rax]
0x1800201ca  shl     edx, 10h
0x1800201cd  movzx   eax, di
0x1800201d0  or      edx, eax
0x1800201d2  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1800201d7  mov     rdx, [rbx+110h]
0x1800201de  inc     edi
0x1800201e0  cmp     edi, [rdx]
0x1800201e2  jb      loc_180020088
0x1800201e8  jmp     loc_180020271
0x1800201ed  mov     r14b, 1
0x1800201f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201f7  lea     rsi, WPP_GLOBAL_Control
0x1800201fe  cmp     rcx, rsi
0x180020201  jz      short loc_180020213
0x180020203  mov     eax, [rcx+2Ch]
0x180020206  test    al, 2
0x180020208  jz      short loc_180020213
0x18002020a  cmp     byte ptr [rcx+29h], 4
0x18002020e  mov     dl, r14b
0x180020211  jnb     short loc_180020216
0x180020213  mov     dl, r15b
0x180020216  lea     rbp, WPP_RECORDER_INITIALIZED
0x18002021d  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x180020224  setnz   r8b
0x180020228  test    dl, dl
0x18002022a  jnz     short loc_180020231
0x18002022c  test    r8b, r8b
0x18002022f  jz      short loc_180020271
0x180020231  mov     rax, [rbx]
0x180020234  mov     r9, [rbx+2A0h]
0x18002023b  mov     rcx, [rcx+18h]
0x18002023f  mov     dword ptr [rsp+0A8h+var_60], 1
0x180020247  mov     [rsp+0A8h+var_68], rax
0x18002024c  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180020253  mov     [rsp+0A8h+var_70], rax
0x180020258  mov     [rsp+0A8h+var_78], 29h ; ')'
0x18002025f  mov     [rsp+0A8h+var_80], 2
0x180020267  mov     [rsp+0A8h+var_88], 4
0x18002026c  call    WPP_RECORDER_AND_TRACE_SF_qL
0x180020271  mov     al, r14b
0x180020274  add     rsp, 78h
0x180020278  pop     r15
0x18002027a  pop     r14
0x18002027c  pop     rdi
0x18002027d  pop     rsi
0x18002027e  pop     rbp
0x18002027f  pop     rbx
0x180020280  retn
```
