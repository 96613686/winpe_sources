# IsCallerAllowedAccess

- ea: `0x14000890c`
- end: `0x140008a21`
- name: `IsCallerAllowedAccess`
- size: `277`
- prototype: `__int64 __fastcall(__int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x140001460`

## callees

- `0x1400020b4`
- `0x1400020e4`
- `0x14000890c`
- `0x140008a28`
- `0x140008c78`

## pseudocode

```c
__int64 __fastcall IsCallerAllowedAccess(__int64 a1, __int64 a2, _BYTE *a3)
{
  int v7; // eax
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  char v11; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  if ( !a3 )
    return 3221225485LL;
  *a3 = 0;
  v7 = IsSpoolerServiceProcess(&v11);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v11 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        goto LABEL_17;
      v10 = 18;
    }
    else
    {
      if ( !(unsigned __int8)IsCallerPrivileged(a1, a2) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
        return 0;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
LABEL_17:
        *a3 = 1;
        return 0;
      }
      v10 = 19;
    }
    WPP_SF_(v9->AttachedDevice, v10, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_decc11c9483a3275477ae1b226799886_Traceguids, (unsigned int)v7);
  return v8;
}

```

## disassembly

```asm
0x14000890c  push    rbx
0x14000890e  push    rbp
0x14000890f  push    rsi
0x140008910  push    rdi
0x140008911  sub     rsp, 28h
0x140008915  mov     [rsp+48h+arg_10], 0
0x14000891a  mov     rdi, r8
0x14000891d  mov     rsi, rdx
0x140008920  mov     rbp, rcx
0x140008923  test    r8, r8
0x140008926  jnz     short loc_140008932
0x140008928  mov     eax, 0C000000Dh
0x14000892d  jmp     loc_140008A17
0x140008932  lea     rcx, [rsp+48h+arg_10]
0x140008937  mov     byte ptr [r8], 0
0x14000893b  call    IsSpoolerServiceProcess
0x140008940  mov     ebx, eax
0x140008942  test    eax, eax
0x140008944  jns     short loc_14000897E
0x140008946  mov     rcx, cs:WPP_GLOBAL_Control
0x14000894d  lea     rdx, WPP_GLOBAL_Control
0x140008954  cmp     rcx, rdx
0x140008957  jz      short loc_140008977
0x140008959  cmp     byte ptr [rcx+29h], 2
0x14000895d  jb      short loc_140008977
0x14000895f  mov     rcx, [rcx+18h]
0x140008963  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x14000896a  mov     edx, 11h
0x14000896f  mov     r9d, eax
0x140008972  call    WPP_SF_D
0x140008977  mov     eax, ebx
0x140008979  jmp     loc_140008A17
0x14000897e  cmp     [rsp+48h+arg_10], 0
0x140008983  jz      short loc_1400089A5
0x140008985  mov     rcx, cs:WPP_GLOBAL_Control
0x14000898c  lea     rdx, WPP_GLOBAL_Control
0x140008993  cmp     rcx, rdx
0x140008996  jz      short loc_1400089E2
0x140008998  cmp     byte ptr [rcx+29h], 4
0x14000899c  jb      short loc_1400089E2
0x14000899e  mov     edx, 12h
0x1400089a3  jmp     short loc_1400089D2
0x1400089a5  mov     rdx, rsi
0x1400089a8  mov     rcx, rbp
0x1400089ab  call    IsCallerPrivileged
0x1400089b0  test    al, al
0x1400089b2  jz      short loc_1400089E7
0x1400089b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089bb  lea     rdx, WPP_GLOBAL_Control
0x1400089c2  cmp     rcx, rdx
0x1400089c5  jz      short loc_1400089E2
0x1400089c7  cmp     byte ptr [rcx+29h], 4
0x1400089cb  jb      short loc_1400089E2
0x1400089cd  mov     edx, 13h
0x1400089d2  mov     rcx, [rcx+18h]
0x1400089d6  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x1400089dd  call    WPP_SF_
0x1400089e2  mov     byte ptr [rdi], 1
0x1400089e5  jmp     short loc_140008A15
0x1400089e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089ee  lea     rdx, WPP_GLOBAL_Control
0x1400089f5  cmp     rcx, rdx
0x1400089f8  jz      short loc_140008A15
0x1400089fa  cmp     byte ptr [rcx+29h], 4
0x1400089fe  jb      short loc_140008A15
0x140008a00  mov     rcx, [rcx+18h]
0x140008a04  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008a0b  mov     edx, 14h
0x140008a10  call    WPP_SF_
0x140008a15  xor     eax, eax
0x140008a17  add     rsp, 28h
0x140008a1b  pop     rdi
0x140008a1c  pop     rsi
0x140008a1d  pop     rbp
0x140008a1e  pop     rbx
0x140008a1f  retn
```
