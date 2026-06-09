# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(ulong,_CEREMONY const *,void *,long)

- ea: `0x180031210`
- end: `0x1800313c4`
- name: `?s_EnumCeremoniesCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXKPEBU_CEREMONY@@PEAXJ@Z`
- size: `436`
- prototype: `void __fastcall(unsigned int, const struct _CEREMONY *, _DWORD *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x180031210`
- `0x180034b50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800313b8`

## pseudocode

```c
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_EnumCeremoniesCompleteCallback(
        unsigned int a1,
        const struct _CEREMONY *a2,
        _DWORD *a3,
        int a4)
{
  _DWORD *v6; // rdi
  const struct _CEREMONY *v7; // rbp
  unsigned int v8; // eax
  bool v9; // dl
  void *v10; // rcx

  v6 = a3;
  v7 = a2;
  if ( a4 >= 0 )
  {
    if ( a1 )
    {
      LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      v6[38] = 0;
      v8 = 10;
      if ( a1 < 0xA )
        v8 = a1;
      v6[39] = v8;
      memcpy_0(v6 + 40, v7, 20LL * v8);
      goto LABEL_28;
    }
    goto LABEL_14;
  }
  if ( !a1 )
  {
LABEL_14:
    v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    goto LABEL_28;
  }
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
LABEL_28:
  v10 = (void *)*((_QWORD *)v6 + 256);
  v6[38] = a4;
  SetEvent(v10);
}

```

## disassembly

```asm
0x180031210  mov     [rsp+arg_0], rbx
0x180031215  mov     [rsp+arg_8], rbp
0x18003121a  mov     [rsp+arg_10], rsi
0x18003121f  push    rdi
0x180031220  sub     rsp, 50h
0x180031224  mov     ebx, ecx
0x180031226  mov     esi, r9d
0x180031229  mov     rdi, r8
0x18003122c  mov     rbp, rdx
0x18003122f  test    r9d, r9d
0x180031232  js      loc_1800312D5
0x180031238  test    ecx, ecx
0x18003123a  jz      loc_1800312D9
0x180031240  mov     rcx, cs:WPP_GLOBAL_Control
0x180031247  lea     rax, WPP_GLOBAL_Control
0x18003124e  cmp     rcx, rax
0x180031251  jz      short loc_18003125D
0x180031253  cmp     byte ptr [rcx+19h], 4
0x180031257  jb      short loc_18003125D
0x180031259  mov     dl, 1
0x18003125b  jmp     short loc_18003125F
0x18003125d  xor     dl, dl
0x18003125f  lea     rax, WPP_RECORDER_INITIALIZED
0x180031266  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003126d  setnz   r8b
0x180031271  test    dl, dl
0x180031273  jnz     short loc_18003127A
0x180031275  test    r8b, r8b
0x180031278  jz      short loc_18003129E
0x18003127a  mov     r9, [rcx+28h]
0x18003127e  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180031285  mov     rcx, [rcx+10h]
0x180031289  mov     [rsp+58h+var_10], ebx
0x18003128d  mov     [rsp+58h+var_20], rax
0x180031292  mov     [rsp+58h+var_28], 5Bh ; '['
0x180031299  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18003129e  and     dword ptr [rdi+98h], 0
0x1800312a5  mov     eax, 0Ah
0x1800312aa  cmp     ebx, eax
0x1800312ac  jnb     short loc_1800312B1
0x1800312ae  mov     rax, rbx
0x1800312b1  mov     eax, eax
0x1800312b3  lea     rcx, [rdi+0A0h]; void *
0x1800312ba  mov     rdx, rbp; Src
0x1800312bd  mov     [rdi+9Ch], eax
0x1800312c3  lea     r8, [rax+rax*4]
0x1800312c7  shl     r8, 2; Size
0x1800312cb  call    memcpy_0
0x1800312d0  jmp     loc_180031397
0x1800312d5  test    ecx, ecx
0x1800312d7  jnz     short loc_180031339
0x1800312d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312e0  lea     rax, WPP_GLOBAL_Control
0x1800312e7  cmp     rcx, rax
0x1800312ea  jz      short loc_1800312F6
0x1800312ec  cmp     byte ptr [rcx+19h], 2
0x1800312f0  jb      short loc_1800312F6
0x1800312f2  mov     dl, 1
0x1800312f4  jmp     short loc_1800312F8
0x1800312f6  xor     dl, dl
0x1800312f8  lea     rax, WPP_RECORDER_INITIALIZED
0x1800312ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180031306  setnz   r8b
0x18003130a  test    dl, dl
0x18003130c  jnz     short loc_180031317
0x18003130e  test    r8b, r8b
0x180031311  jz      loc_180031397
0x180031317  mov     r9, [rcx+28h]
0x18003131b  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180031322  mov     rcx, [rcx+10h]
0x180031326  mov     [rsp+58h+var_20], rax
0x18003132b  mov     [rsp+58h+var_28], 5Ch ; '\'
0x180031332  call    WPP_RECORDER_AND_TRACE_SF_s
0x180031337  jmp     short loc_180031397
0x180031339  mov     rcx, cs:WPP_GLOBAL_Control
0x180031340  lea     rax, WPP_GLOBAL_Control
0x180031347  cmp     rcx, rax
0x18003134a  jz      short loc_180031356
0x18003134c  cmp     byte ptr [rcx+19h], 2
0x180031350  jb      short loc_180031356
0x180031352  mov     dl, 1
0x180031354  jmp     short loc_180031358
0x180031356  xor     dl, dl
0x180031358  lea     rax, WPP_RECORDER_INITIALIZED
0x18003135f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180031366  setnz   r8b
0x18003136a  test    dl, dl
0x18003136c  jnz     short loc_180031373
0x18003136e  test    r8b, r8b
0x180031371  jz      short loc_180031397
0x180031373  mov     r9, [rcx+28h]
0x180031377  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18003137e  mov     rcx, [rcx+10h]
0x180031382  mov     [rsp+58h+var_10], esi
0x180031386  mov     [rsp+58h+var_20], rax
0x18003138b  mov     [rsp+58h+var_28], 5Dh ; ']'
0x180031392  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180031397  mov     rcx, [rdi+800h]
0x18003139e  mov     [rdi+98h], esi
0x1800313a4  mov     rbx, [rsp+58h+arg_0]
0x1800313a9  mov     rbp, [rsp+58h+arg_8]
0x1800313ae  mov     rsi, [rsp+58h+arg_10]
0x1800313b3  add     rsp, 50h
0x1800313b7  pop     rdi
0x1800313b8  jmp     cs:__imp_SetEvent
```
