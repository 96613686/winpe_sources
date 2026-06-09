# CInterfaceMonitor::NsiInterfaceChangeCallback(void *,_NSI_KEYSTRUCT_DESC *,_NSI_SINGLE_PARAM_DESC *,_NSI_NOTIFICATION)

- ea: `0x18002ac60`
- end: `0x18002ade9`
- name: `?NsiInterfaceChangeCallback@CInterfaceMonitor@@CAXPEAXPEAU_NSI_KEYSTRUCT_DESC@@PEAU_NSI_SINGLE_PARAM_DESC@@W4_NSI_NOTIFICATION@@@Z`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000ca20`
- `0x18002ac60`
- `0x1800695d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ace0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ace0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ad1a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002acfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002acfa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002ad0a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002ad0a`

## pseudocode

```c
void __fastcall CInterfaceMonitor::NsiInterfaceChangeCallback(__int64 a1, _QWORD **a2, __int64 a3, int a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // eax
  _DWORD *v10; // rdx
  __int64 v11; // r8
  struct _TP_WORK *v12; // rcx
  __int64 v13; // rdx

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( !a4 && *(_DWORD *)a3 == 1 && *(_DWORD *)(a3 + 20) == 536 )
    {
      v9 = *(_DWORD *)(a3 + 16);
      if ( v9 >= 4 )
      {
        v10 = *(_DWORD **)(a3 + 8);
        v11 = 0;
        if ( v9 >= 8 )
          v11 = (unsigned int)v10[1];
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 6u )
          WPP_SF_idD(v8[2], v10, v11, **a2, *v10, v11);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        v12 = *(struct _TP_WORK **)(a1 + 8);
        if ( v12 )
        {
          WaitForThreadpoolWorkCallbacks(v12, 1);
          SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 8));
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 88));
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
        {
          v13 = 30;
LABEL_18:
          WPP_SF_(v8[2], v13, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
        }
      }
    }
  }
  else if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x10) != 0 && *((_BYTE *)v8 + 25) >= 6u )
  {
    v13 = 28;
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x18002ac60  push    rbx
0x18002ac62  push    rbp
0x18002ac63  push    rsi
0x18002ac64  push    rdi
0x18002ac65  push    r14
0x18002ac67  sub     rsp, 30h
0x18002ac6b  mov     edi, r9d
0x18002ac6e  mov     rsi, r8
0x18002ac71  mov     r14, rdx
0x18002ac74  mov     rbx, rcx
0x18002ac77  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac7e  lea     rbp, WPP_GLOBAL_Control
0x18002ac85  cmp     rcx, rbp
0x18002ac88  jz      short loc_18002AC94
0x18002ac8a  test    byte ptr [rcx+1Ch], 10h
0x18002ac8e  jnz     loc_18002AD64
0x18002ac94  test    rbx, rbx
0x18002ac97  jz      loc_18002ADC2
0x18002ac9d  test    edi, edi
0x18002ac9f  jz      short loc_18002ACAD
0x18002aca1  add     rsp, 30h
0x18002aca5  pop     r14
0x18002aca7  pop     rdi
0x18002aca8  pop     rsi
0x18002aca9  pop     rbp
0x18002acaa  pop     rbx
0x18002acab  retn
0x18002acad  cmp     dword ptr [rsi], 1
0x18002acb0  jnz     short loc_18002ACA1
0x18002acb2  cmp     dword ptr [rsi+14h], 218h
0x18002acb9  jnz     short loc_18002ACA1
0x18002acbb  mov     eax, [rsi+10h]
0x18002acbe  cmp     eax, 4
0x18002acc1  jb      short loc_18002ACA1
0x18002acc3  mov     rdx, [rsi+8]
0x18002acc7  xor     r8d, r8d
0x18002acca  cmp     eax, 8
0x18002accd  jb      short loc_18002ACD3
0x18002accf  mov     r8d, [rdx+4]
0x18002acd3  cmp     rcx, rbp
0x18002acd6  jnz     loc_18002AD8F
0x18002acdc  lea     rcx, [rbx+58h]; lpCriticalSection
0x18002ace0  call    cs:__imp_EnterCriticalSection
0x18002ace7  nop     dword ptr [rax+rax+00h]
0x18002acec  mov     rcx, [rbx+8]; pwk
0x18002acf0  test    rcx, rcx
0x18002acf3  jz      short loc_18002AD16
0x18002acf5  mov     edx, 1; fCancelPendingCallbacks
0x18002acfa  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002ad01  nop     dword ptr [rax+rax+00h]
0x18002ad06  mov     rcx, [rbx+8]; pwk
0x18002ad0a  call    cs:__imp_SubmitThreadpoolWork
0x18002ad11  nop     dword ptr [rax+rax+00h]
0x18002ad16  lea     rcx, [rbx+58h]; lpCriticalSection
0x18002ad1a  call    cs:__imp_LeaveCriticalSection
0x18002ad21  nop     dword ptr [rax+rax+00h]
0x18002ad26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad2d  cmp     rcx, rbp
0x18002ad30  jz      loc_18002ACA1
0x18002ad36  test    byte ptr [rcx+1Ch], 10h
0x18002ad3a  jz      loc_18002ACA1
0x18002ad40  cmp     byte ptr [rcx+19h], 6
0x18002ad44  jb      loc_18002ACA1
0x18002ad4a  mov     edx, 1Eh
0x18002ad4f  mov     rcx, [rcx+10h]
0x18002ad53  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18002ad5a  call    WPP_SF_
0x18002ad5f  jmp     loc_18002ACA1
0x18002ad64  cmp     byte ptr [rcx+19h], 6
0x18002ad68  jb      loc_18002AC94
0x18002ad6e  mov     rcx, [rcx+10h]
0x18002ad72  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18002ad79  mov     edx, 1Bh
0x18002ad7e  call    WPP_SF_
0x18002ad83  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad8a  jmp     loc_18002AC94
0x18002ad8f  test    byte ptr [rcx+1Ch], 10h
0x18002ad93  jz      loc_18002ACDC
0x18002ad99  cmp     byte ptr [rcx+19h], 6
0x18002ad9d  jb      loc_18002ACDC
0x18002ada3  mov     r9, [r14]
0x18002ada6  mov     eax, [rdx]
0x18002ada8  mov     rcx, [rcx+10h]
0x18002adac  mov     [rsp+58h+var_30], r8d
0x18002adb1  mov     r9, [r9]
0x18002adb4  mov     [rsp+58h+var_38], eax
0x18002adb8  call    WPP_SF_idD
0x18002adbd  jmp     loc_18002ACDC
0x18002adc2  cmp     rcx, rbp
0x18002adc5  jz      loc_18002ACA1
0x18002adcb  test    byte ptr [rcx+1Ch], 10h
0x18002adcf  jz      loc_18002ACA1
0x18002add5  cmp     byte ptr [rcx+19h], 6
0x18002add9  jb      loc_18002ACA1
0x18002addf  mov     edx, 1Ch
0x18002ade4  jmp     loc_18002AD4F
```
