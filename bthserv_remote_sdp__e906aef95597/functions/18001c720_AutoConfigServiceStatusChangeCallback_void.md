# AutoConfigServiceStatusChangeCallback(void *)

- ea: `0x18001c720`
- end: `0x18001ca36`
- name: `?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z`
- size: `790`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001d1a8`

## callees

- `0x180012004`
- `0x1800120b8`
- `0x18001c720`
- `0x18001cf10`
- `0x18001d448`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001c8b9`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001c97e`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001c8b9`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001c97e`

## pseudocode

```c
void __fastcall AutoConfigServiceStatusChangeCallback(_DWORD *a1)
{
  _BYTE *v2; // rcx
  char v3; // bl
  bool v4; // dl
  bool v5; // dl
  bool v6; // r8
  int v7; // edx
  bool v8; // dl
  int v9; // edx
  int v10; // r8d
  bool v11; // dl
  int v12; // edx
  int v13; // r8d

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1[6] )
  {
    v5 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 3u;
    v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
  }
  else
  {
    v7 = a1[8];
    if ( *((_DWORD *)pInterfaceGuid + 29) != v7 )
    {
      *((_DWORD *)pInterfaceGuid + 29) = v7;
      if ( a1[8] == 1 )
      {
        v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        CloseWlanApi();
        if ( !NotifyServiceStatusChangeW(
                *((SC_HANDLE *)pInterfaceGuid + 13),
                8u,
                (PSERVICE_NOTIFYW)((char *)pInterfaceGuid + 16)) )
          goto LABEL_58;
        v2 = WPP_GLOBAL_Control;
        LOBYTE(v12) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
          goto LABEL_58;
        }
      }
      else
      {
        if ( a1[8] != 4 )
          goto LABEL_58;
        v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        if ( (unsigned int)OpenWlanApi() )
        {
          if ( NotifyServiceStatusChangeW(
                 *((SC_HANDLE *)pInterfaceGuid + 13),
                 1u,
                 (PSERVICE_NOTIFYW)((char *)pInterfaceGuid + 16)) )
          {
            LOBYTE(v9) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
            if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v9,
                v10,
                *((_QWORD *)WPP_GLOBAL_Control + 5));
            }
            CloseWlanApi();
          }
          goto LABEL_58;
        }
        v2 = WPP_GLOBAL_Control;
        v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_15:
          WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v2 + 2), v5, v6, *((_QWORD *)v2 + 5));
LABEL_58:
          v2 = WPP_GLOBAL_Control;
        }
      }
    }
  }
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || v2[25] < 4u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
}

```

## disassembly

```asm
0x18001c720  mov     rax, rsp
0x18001c723  mov     [rax+8], rbx
0x18001c727  mov     [rax+10h], rbp
0x18001c72b  mov     [rax+18h], rsi
0x18001c72f  mov     [rax+20h], rdi
0x18001c733  push    r15
0x18001c735  sub     rsp, 50h
0x18001c739  mov     rdi, rcx
0x18001c73c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c743  lea     rsi, WPP_GLOBAL_Control
0x18001c74a  mov     ebx, 1
0x18001c74f  cmp     rcx, rsi
0x18001c752  jz      short loc_18001C75E
0x18001c754  cmp     byte ptr [rcx+19h], 4
0x18001c758  jb      short loc_18001C75E
0x18001c75a  mov     dl, bl
0x18001c75c  jmp     short loc_18001C760
0x18001c75e  xor     dl, dl
0x18001c760  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001c767  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c76e  lea     r15, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001c775  setnz   r8b
0x18001c779  test    dl, dl
0x18001c77b  jnz     short loc_18001C782
0x18001c77d  test    r8b, r8b
0x18001c780  jz      short loc_18001C7A2
0x18001c782  mov     r9, [rcx+28h]
0x18001c786  mov     rcx, [rcx+10h]
0x18001c78a  mov     [rsp+58h+var_20], r15
0x18001c78f  mov     [rsp+58h+var_28], 13h
0x18001c796  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c79b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c7a2  cmp     dword ptr [rdi+18h], 0
0x18001c7a6  jz      short loc_18001C7EF
0x18001c7a8  cmp     rcx, rsi
0x18001c7ab  jz      short loc_18001C7B7
0x18001c7ad  cmp     byte ptr [rcx+19h], 3
0x18001c7b1  jb      short loc_18001C7B7
0x18001c7b3  mov     dl, bl
0x18001c7b5  jmp     short loc_18001C7B9
0x18001c7b7  xor     dl, dl
0x18001c7b9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c7c0  setnz   r8b
0x18001c7c4  test    dl, dl
0x18001c7c6  jnz     short loc_18001C7D1
0x18001c7c8  test    r8b, r8b
0x18001c7cb  jz      loc_18001C9DE
0x18001c7d1  mov     [rsp+58h+var_20], r15
0x18001c7d6  mov     [rsp+58h+var_28], 14h
0x18001c7dd  mov     r9, [rcx+28h]
0x18001c7e1  mov     rcx, [rcx+10h]
0x18001c7e5  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c7ea  jmp     loc_18001C9D7
0x18001c7ef  mov     rax, cs:pInterfaceGuid
0x18001c7f6  mov     edx, [rdi+20h]
0x18001c7f9  cmp     [rax+74h], edx
0x18001c7fc  jz      loc_18001C9DE
0x18001c802  mov     [rax+74h], edx
0x18001c805  mov     ecx, [rdi+20h]
0x18001c808  sub     ecx, ebx
0x18001c80a  jz      loc_18001C920
0x18001c810  cmp     ecx, 3
0x18001c813  jnz     loc_18001C9D7
0x18001c819  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c820  cmp     rcx, rsi
0x18001c823  jz      short loc_18001C82F
0x18001c825  cmp     byte ptr [rcx+19h], 4
0x18001c829  jb      short loc_18001C82F
0x18001c82b  mov     dl, bl
0x18001c82d  jmp     short loc_18001C831
0x18001c82f  xor     dl, dl
0x18001c831  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c838  setnz   r8b
0x18001c83c  test    dl, dl
0x18001c83e  jnz     short loc_18001C845
0x18001c840  test    r8b, r8b
0x18001c843  jz      short loc_18001C85E
0x18001c845  mov     r9, [rcx+28h]
0x18001c849  mov     rcx, [rcx+10h]
0x18001c84d  mov     [rsp+58h+var_20], r15
0x18001c852  mov     [rsp+58h+var_28], 15h
0x18001c859  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c85e  call    ?OpenWlanApi@@YAHXZ; OpenWlanApi(void)
0x18001c863  test    eax, eax
0x18001c865  jnz     short loc_18001C8A8
0x18001c867  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c86e  cmp     rcx, rsi
0x18001c871  jz      short loc_18001C87D
0x18001c873  cmp     byte ptr [rcx+19h], 3
0x18001c877  jb      short loc_18001C87D
0x18001c879  mov     dl, bl
0x18001c87b  jmp     short loc_18001C87F
0x18001c87d  xor     dl, dl
0x18001c87f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c886  setnz   r8b
0x18001c88a  test    dl, dl
0x18001c88c  jnz     short loc_18001C897
0x18001c88e  test    r8b, r8b
0x18001c891  jz      loc_18001C9DE
0x18001c897  mov     [rsp+58h+var_20], r15
0x18001c89c  mov     [rsp+58h+var_28], 16h
0x18001c8a3  jmp     loc_18001C7DD
0x18001c8a8  mov     rcx, cs:pInterfaceGuid
0x18001c8af  mov     edx, ebx; dwNotifyMask
0x18001c8b1  lea     r8, [rcx+10h]; pNotifyBuffer
0x18001c8b5  mov     rcx, [rcx+68h]; hService
0x18001c8b9  call    cs:__imp_NotifyServiceStatusChangeW
0x18001c8c0  nop     dword ptr [rax+rax+00h]
0x18001c8c5  test    eax, eax
0x18001c8c7  jz      loc_18001C9D7
0x18001c8cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8d4  cmp     rcx, rsi
0x18001c8d7  jz      short loc_18001C8E3
0x18001c8d9  cmp     byte ptr [rcx+19h], 3
0x18001c8dd  jb      short loc_18001C8E3
0x18001c8df  mov     dl, bl
0x18001c8e1  jmp     short loc_18001C8E5
0x18001c8e3  xor     dl, dl
0x18001c8e5  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c8ec  setnz   r8b
0x18001c8f0  test    dl, dl
0x18001c8f2  jnz     short loc_18001C8F9
0x18001c8f4  test    r8b, r8b
0x18001c8f7  jz      short loc_18001C916
0x18001c8f9  mov     r9, [rcx+28h]
0x18001c8fd  mov     rcx, [rcx+10h]
0x18001c901  mov     [rsp+58h+var_10], eax
0x18001c905  mov     [rsp+58h+var_20], r15
0x18001c90a  mov     [rsp+58h+var_28], 17h
0x18001c911  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001c916  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001c91b  jmp     loc_18001C9D7
0x18001c920  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c927  cmp     rcx, rsi
0x18001c92a  jz      short loc_18001C936
0x18001c92c  cmp     byte ptr [rcx+19h], 4
0x18001c930  jb      short loc_18001C936
0x18001c932  mov     dl, bl
0x18001c934  jmp     short loc_18001C938
0x18001c936  xor     dl, dl
0x18001c938  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c93f  setnz   r8b
0x18001c943  test    dl, dl
0x18001c945  jnz     short loc_18001C94C
0x18001c947  test    r8b, r8b
0x18001c94a  jz      short loc_18001C965
0x18001c94c  mov     r9, [rcx+28h]
0x18001c950  mov     rcx, [rcx+10h]
0x18001c954  mov     [rsp+58h+var_20], r15
0x18001c959  mov     [rsp+58h+var_28], 18h
0x18001c960  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001c965  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001c96a  mov     rcx, cs:pInterfaceGuid
0x18001c971  mov     edx, 8; dwNotifyMask
0x18001c976  lea     r8, [rcx+10h]; pNotifyBuffer
0x18001c97a  mov     rcx, [rcx+68h]; hService
0x18001c97e  call    cs:__imp_NotifyServiceStatusChangeW
0x18001c985  nop     dword ptr [rax+rax+00h]
0x18001c98a  test    eax, eax
0x18001c98c  jz      short loc_18001C9D7
0x18001c98e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c995  cmp     rcx, rsi
0x18001c998  jz      short loc_18001C9A4
0x18001c99a  cmp     byte ptr [rcx+19h], 3
0x18001c99e  jb      short loc_18001C9A4
0x18001c9a0  mov     dl, bl
0x18001c9a2  jmp     short loc_18001C9A6
0x18001c9a4  xor     dl, dl
0x18001c9a6  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c9ad  setnz   r8b
0x18001c9b1  test    dl, dl
0x18001c9b3  jnz     short loc_18001C9BA
0x18001c9b5  test    r8b, r8b
0x18001c9b8  jz      short loc_18001C9DE
0x18001c9ba  mov     r9, [rcx+28h]
0x18001c9be  mov     rcx, [rcx+10h]
0x18001c9c2  mov     [rsp+58h+var_10], eax
0x18001c9c6  mov     [rsp+58h+var_20], r15
0x18001c9cb  mov     [rsp+58h+var_28], 19h
0x18001c9d2  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001c9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9de  cmp     rcx, rsi
0x18001c9e1  jz      short loc_18001C9E9
0x18001c9e3  cmp     byte ptr [rcx+19h], 4
0x18001c9e7  jnb     short loc_18001C9EB
0x18001c9e9  xor     bl, bl
0x18001c9eb  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001c9f2  setnz   r8b
0x18001c9f6  test    bl, bl
0x18001c9f8  jnz     short loc_18001C9FF
0x18001c9fa  test    r8b, r8b
0x18001c9fd  jz      short loc_18001CA1A
0x18001c9ff  mov     r9, [rcx+28h]
0x18001ca03  mov     dl, bl
0x18001ca05  mov     rcx, [rcx+10h]
0x18001ca09  mov     [rsp+58h+var_20], r15
0x18001ca0e  mov     [rsp+58h+var_28], 1Ah
0x18001ca15  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ca1a  mov     rbx, [rsp+58h+arg_0]
0x18001ca1f  mov     rbp, [rsp+58h+arg_8]
0x18001ca24  mov     rsi, [rsp+58h+arg_10]
0x18001ca29  mov     rdi, [rsp+58h+arg_18]
0x18001ca2e  add     rsp, 50h
0x18001ca32  pop     r15
0x18001ca34  retn
```
