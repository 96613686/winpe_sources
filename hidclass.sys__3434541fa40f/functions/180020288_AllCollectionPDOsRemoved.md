# AllCollectionPDOsRemoved

- ea: `0x180020288`
- end: `0x1800204b6`
- name: `AllCollectionPDOsRemoved`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019694`

## callees

- `0x18000ddc8`
- `0x18001c8a0`
- `0x180020288`
- `0x180022a68`
- `0x180023338`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x1800202a8`
- `ntoskrnl!MmBadPointer` at `0x1800202ec`

## string_xrefs

- `0x1800203e1`: `Unexpected/invalid PDO extension`

## pseudocode

```c
char __fastcall AllCollectionPDOsRemoved(__int64 a1)
{
  int *v1; // rdx
  char v3; // bl
  char v4; // r15
  __int64 v5; // rsi
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // edx
  PDEVICE_OBJECT v9; // rcx
  bool v10; // r10
  int v11; // eax
  int v13; // [rsp+20h] [rbp-88h]
  int v14; // [rsp+28h] [rbp-80h]
  int v15; // [rsp+30h] [rbp-78h]
  int v16; // [rsp+38h] [rbp-70h]
  int v17; // [rsp+58h] [rbp-50h]

  v1 = *(int **)(a1 + 272);
  if ( v1 && v1 != MmBadPointer )
  {
    v3 = 1;
    v4 = 1;
    if ( !*v1 )
      return v4;
    v5 = 0;
    while ( 1 )
    {
      v6 = *(_QWORD *)&v1[2 * v5 + 2];
      v7 = *(_QWORD *)(v6 + 64) + 32LL;
      if ( *(_QWORD *)(v6 + 64) == -32 || (PVOID)v7 == MmBadPointer )
      {
        v9 = WPP_GLOBAL_Control;
        v10 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v11 = *v1;
          LOBYTE(v1) = v10;
          WPP_RECORDER_AND_TRACE_SF_qqDD(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v1,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *(_QWORD *)(a1 + 672),
            v13,
            v14,
            45,
            v16,
            *(_QWORD *)a1,
            v6,
            v11,
            v5);
        }
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v9,
          (unsigned int)(unsigned __int16)v5 | (**(_DWORD **)(a1 + 272) << 16),
          *(unsigned __int16 *)(a1 + 110) | (*(unsigned __int16 *)(a1 + 108) << 16),
          "Unexpected/invalid PDO extension");
      }
      else
      {
        v8 = *(_DWORD *)(*(_QWORD *)(v6 + 64) + 36LL);
        if ( v8 != 7 )
        {
          v4 = 0;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v3 = 0;
          }
          if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v8) = v3;
            WPP_RECORDER_AND_TRACE_SF_qdqDL(
              WPP_GLOBAL_Control->AttachedDevice,
              v8,
              WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
              *(_QWORD *)(a1 + 672),
              v13,
              v14,
              v15,
              v16,
              *(_QWORD *)(*(_QWORD *)(v7 + 64) + 32LL),
              *(_DWORD *)(v7 + 8),
              *(_QWORD *)(v7 + 48),
              v17,
              *(_DWORD *)(v7 + 4));
          }
          return v4;
        }
      }
      v1 = *(int **)(a1 + 272);
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= *v1 )
        return v4;
    }
  }
  v4 = 1;
  LOBYTE(v1) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qL(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *(_QWORD *)(a1 + 672),
      4,
      2,
      44,
      (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
      *(_QWORD *)a1,
      1);
  return v4;
}

```

## disassembly

```asm
0x180020288  push    rbx
0x18002028a  push    rbp
0x18002028b  push    rsi
0x18002028c  push    rdi
0x18002028d  push    r14
0x18002028f  push    r15
0x180020291  sub     rsp, 78h
0x180020295  mov     rdx, [rcx+110h]
0x18002029c  mov     rdi, rcx
0x18002029f  test    rdx, rdx
0x1800202a2  jz      loc_180020420
0x1800202a8  mov     rax, cs:MmBadPointer
0x1800202af  cmp     rdx, [rax]
0x1800202b2  jz      loc_180020420
0x1800202b8  cmp     dword ptr [rdx], 0
0x1800202bb  mov     ebx, 1
0x1800202c0  mov     r15b, bl
0x1800202c3  jbe     loc_1800204A5
0x1800202c9  xor     esi, esi
0x1800202cb  lea     rbp, WPP_GLOBAL_Control
0x1800202d2  lea     r14, WPP_RECORDER_INITIALIZED
0x1800202d9  mov     r9, [rdx+rsi*8+8]
0x1800202de  mov     rcx, [r9+40h]
0x1800202e2  add     rcx, 20h ; ' '
0x1800202e6  jz      loc_180020374
0x1800202ec  mov     rax, cs:MmBadPointer
0x1800202f3  cmp     rcx, [rax]
0x1800202f6  jz      short loc_180020374
0x1800202f8  mov     edx, [rcx+4]
0x1800202fb  cmp     edx, 7
0x1800202fe  jz      loc_18002040A
0x180020304  xor     r15b, r15b
0x180020307  mov     r10, cs:WPP_GLOBAL_Control
0x18002030e  cmp     r10, rbp
0x180020311  jz      short loc_180020322
0x180020313  mov     eax, [r10+2Ch]
0x180020317  test    al, 2
0x180020319  jz      short loc_180020322
0x18002031b  cmp     byte ptr [r10+29h], 4
0x180020320  jnb     short loc_180020324
0x180020322  xor     bl, bl
0x180020324  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002032b  setnz   r8b
0x18002032f  test    bl, bl
0x180020331  jnz     short loc_18002033C
0x180020333  test    r8b, r8b
0x180020336  jz      loc_1800204A5
0x18002033c  mov     rax, [rcx+30h]
0x180020340  mov     r9, [rcx+40h]
0x180020344  mov     [rsp+0A8h+var_48], edx
0x180020348  mov     dl, bl
0x18002034a  mov     [rsp+0A8h+var_58], rax
0x18002034f  mov     eax, [rcx+8]
0x180020352  mov     rcx, [r10+18h]
0x180020356  mov     dword ptr [rsp+0A8h+var_60], eax
0x18002035a  mov     rax, [r9+20h]
0x18002035e  mov     r9, [rdi+2A0h]
0x180020365  mov     [rsp+0A8h+var_68], rax
0x18002036a  call    WPP_RECORDER_AND_TRACE_SF_qdqDL
0x18002036f  jmp     loc_1800204A5
0x180020374  mov     rcx, cs:WPP_GLOBAL_Control
0x18002037b  cmp     rcx, rbp
0x18002037e  jz      short loc_180020394
0x180020380  test    dword ptr [rcx+2Ch], 100h
0x180020387  jz      short loc_180020394
0x180020389  cmp     byte ptr [rcx+29h], 2
0x18002038d  jb      short loc_180020394
0x18002038f  mov     r10b, bl
0x180020392  jmp     short loc_180020397
0x180020394  xor     r10b, r10b
0x180020397  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002039e  setnz   r8b
0x1800203a2  test    r10b, r10b
0x1800203a5  jnz     short loc_1800203AC
0x1800203a7  test    r8b, r8b
0x1800203aa  jz      short loc_1800203DD
0x1800203ac  mov     eax, [rdx]
0x1800203ae  mov     dl, r10b
0x1800203b1  mov     rcx, [rcx+18h]
0x1800203b5  mov     [rsp+0A8h+var_50], esi
0x1800203b9  mov     dword ptr [rsp+0A8h+var_58], eax
0x1800203bd  mov     rax, [rdi]
0x1800203c0  mov     [rsp+0A8h+var_60], r9
0x1800203c5  mov     r9, [rdi+2A0h]
0x1800203cc  mov     [rsp+0A8h+var_68], rax
0x1800203d1  mov     [rsp+0A8h+var_78], 2Dh ; '-'
0x1800203d8  call    WPP_RECORDER_AND_TRACE_SF_qqDD
0x1800203dd  movzx   eax, word ptr [rdi+6Eh]; __annotation("Debug", "TelemetryAssert", "FALSE", "Unexpected/invalid PDO extension")
0x1800203e1  lea     r9, aUnexpectedInva; "Unexpected/invalid PDO extension"
0x1800203e8  movzx   r8d, word ptr [rdi+6Ch]
0x1800203ed  shl     r8d, 10h
0x1800203f1  or      r8d, eax
0x1800203f4  mov     rax, [rdi+110h]
0x1800203fb  mov     edx, [rax]
0x1800203fd  shl     edx, 10h
0x180020400  movzx   eax, si
0x180020403  or      edx, eax
0x180020405  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x18002040a  mov     rdx, [rdi+110h]
0x180020411  add     esi, ebx
0x180020413  cmp     esi, [rdx]
0x180020415  jb      loc_1800202D9
0x18002041b  jmp     loc_1800204A5
0x180020420  mov     ebx, 1
0x180020425  mov     r15b, bl
0x180020428  mov     rcx, cs:WPP_GLOBAL_Control
0x18002042f  lea     rbp, WPP_GLOBAL_Control
0x180020436  cmp     rcx, rbp
0x180020439  jz      short loc_18002044C
0x18002043b  mov     eax, [rcx+2Ch]
0x18002043e  test    al, 2
0x180020440  jz      short loc_18002044C
0x180020442  cmp     byte ptr [rcx+29h], 4
0x180020446  jb      short loc_18002044C
0x180020448  mov     dl, bl
0x18002044a  jmp     short loc_18002044E
0x18002044c  xor     dl, dl
0x18002044e  lea     r14, WPP_RECORDER_INITIALIZED
0x180020455  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18002045c  setnz   r8b
0x180020460  test    dl, dl
0x180020462  jnz     short loc_180020469
0x180020464  test    r8b, r8b
0x180020467  jz      short loc_1800204A5
0x180020469  mov     rax, [rdi]
0x18002046c  mov     r9, [rdi+2A0h]
0x180020473  mov     rcx, [rcx+18h]
0x180020477  mov     dword ptr [rsp+0A8h+var_60], ebx
0x18002047b  mov     [rsp+0A8h+var_68], rax
0x180020480  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180020487  mov     [rsp+0A8h+var_70], rax
0x18002048c  mov     [rsp+0A8h+var_78], 2Ch ; ','
0x180020493  mov     [rsp+0A8h+var_80], 2
0x18002049b  mov     [rsp+0A8h+var_88], 4
0x1800204a0  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800204a5  mov     al, r15b
0x1800204a8  add     rsp, 78h
0x1800204ac  pop     r15
0x1800204ae  pop     r14
0x1800204b0  pop     rdi
0x1800204b1  pop     rsi
0x1800204b2  pop     rbp
0x1800204b3  pop     rbx
0x1800204b4  retn
```
