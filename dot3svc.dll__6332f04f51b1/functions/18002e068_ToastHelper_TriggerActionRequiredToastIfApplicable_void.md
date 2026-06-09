# ToastHelper::TriggerActionRequiredToastIfApplicable(void)

- ea: `0x18002e068`
- end: `0x18002e17f`
- name: `?TriggerActionRequiredToastIfApplicable@ToastHelper@@QEAAJXZ`
- size: `279`
- prototype: `__int64 __fastcall(ToastHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a9ec`

## callees

- `0x1800084ec`
- `0x18000c230`
- `0x18002888c`
- `0x18002da30`
- `0x18002e068`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002e102`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002e102`

## pseudocode

```c
__int64 __fastcall ToastHelper::TriggerActionRequiredToastIfApplicable(ToastHelper *this)
{
  unsigned int v2; // ebx
  __int64 *v3; // rax
  __int64 v4; // rdi
  volatile signed __int32 *v5; // rcx
  int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  volatile signed __int32 *v9; // [rsp+40h] [rbp+8h] BYREF
  ToastHelper *v10; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 13, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
  }
  v10 = this;
  v2 = *((_DWORD *)this + 8);
  v3 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_068e8eea85672025190c8dfc113d2115_____lambda_068e8eea85672025190c8dfc113d2115___(
                    &v9,
                    &v10);
  v4 = *v3;
  *v3 = 0;
  v5 = v9;
  if ( v9 )
  {
    v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
  }
  v6 = SHTaskPoolQueueTask(0, 2, v2);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v6 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5F,
      (int)"onecoreuap\\net\\dot3\\ac\\server\\toasthelper.cpp",
      (const char *)(unsigned int)v6);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18002e068  mov     [rsp+arg_10], rbx
0x18002e06d  mov     [rsp+arg_18], rbp
0x18002e072  push    rdi
0x18002e073  sub     rsp, 30h
0x18002e077  mov     rbx, rcx
0x18002e07a  lea     rbp, WPP_GLOBAL_Control
0x18002e081  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e088  cmp     rcx, rbp
0x18002e08b  jz      short loc_18002E0AE
0x18002e08d  cmp     byte ptr [rcx+19h], 4
0x18002e091  jb      short loc_18002E0AE
0x18002e093  test    byte ptr [rcx+1Ch], 1
0x18002e097  jz      short loc_18002E0AE
0x18002e099  mov     edx, 0Dh
0x18002e09e  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002e0a5  mov     rcx, [rcx+10h]
0x18002e0a9  call    WPP_SF_
0x18002e0ae  mov     [rsp+38h+arg_8], rbx
0x18002e0b3  mov     ebx, [rbx+20h]
0x18002e0b6  nop
0x18002e0b7  lea     rdx, [rsp+38h+arg_8]
0x18002e0bc  lea     rcx, [rsp+38h+arg_0]
0x18002e0c1  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_068e8eea85672025190c8dfc113d2115_____lambda_068e8eea85672025190c8dfc113d2115___
0x18002e0c6  mov     rdi, [rax]
0x18002e0c9  mov     qword ptr [rax], 0
0x18002e0d0  mov     rcx, [rsp+38h+arg_0]
0x18002e0d5  test    rcx, rcx
0x18002e0d8  jz      short loc_18002E0E8
0x18002e0da  mov     [rsp+38h+arg_0], 0
0x18002e0e3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002e0e8  mov     [rsp+38h+var_10], 0
0x18002e0f1  mov     qword ptr [rsp+38h+var_18], rdi; int
0x18002e0f6  xor     r9d, r9d
0x18002e0f9  mov     r8d, ebx
0x18002e0fc  lea     edx, [r9+2]
0x18002e100  xor     ecx, ecx
0x18002e102  call    cs:__imp_SHTaskPoolQueueTask
0x18002e108  mov     ebx, eax
0x18002e10a  test    rdi, rdi
0x18002e10d  jz      short loc_18002E11F
0x18002e10f  mov     rdx, [rdi]
0x18002e112  mov     rcx, rdi
0x18002e115  mov     rax, [rdx+10h]
0x18002e119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e11e  nop
0x18002e11f  test    ebx, ebx
0x18002e121  jns     short loc_18002E140
0x18002e123  mov     rcx, [rsp+38h]; this
0x18002e128  mov     r9d, ebx; char *
0x18002e12b  lea     r8, aOnecoreuapNetD_1; "onecoreuap\\net\\dot3\\ac\\server\\toas"...
0x18002e132  mov     edx, 5Fh ; '_'; void *
0x18002e137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e13c  mov     eax, ebx
0x18002e13e  jmp     short loc_18002E16F
0x18002e140  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e147  cmp     rcx, rbp
0x18002e14a  jz      short loc_18002E16D
0x18002e14c  cmp     byte ptr [rcx+19h], 4
0x18002e150  jb      short loc_18002E16D
0x18002e152  test    byte ptr [rcx+1Ch], 1
0x18002e156  jz      short loc_18002E16D
0x18002e158  mov     edx, 0Eh
0x18002e15d  lea     r8, WPP_9b988db5ce2f34186259e8bb867b7549_Traceguids
0x18002e164  mov     rcx, [rcx+10h]
0x18002e168  call    WPP_SF_
0x18002e16d  xor     eax, eax
0x18002e16f  mov     rbx, [rsp+38h+arg_10]
0x18002e174  mov     rbp, [rsp+38h+arg_18]
0x18002e179  add     rsp, 30h
0x18002e17d  pop     rdi
0x18002e17e  retn
```
