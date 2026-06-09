# Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(ulong)

- ea: `0x180048d4c`
- end: `0x180048de7`
- name: `?put_CompletedSteps@CTaskTimeEstimator@Imapi2Utility@@QEAAXK@Z`
- size: `155`
- prototype: `void __fastcall(Imapi2Utility::CTaskTimeEstimator *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800263d0`
- `0x180027df0`
- `0x1800437d8`

## callees

- `0x180014134`
- `0x180048034`
- `0x180048d4c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180048d76`
- `KERNEL32!GetTickCount` at `0x180048d76`

## pseudocode

```c
void __fastcall Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(
        Imapi2Utility::CTaskTimeEstimator *this,
        unsigned int a2)
{
  int v3; // ebx

  if ( a2 >= *((_DWORD *)this + 5) )
    a2 = *((_DWORD *)this + 5);
  *((_DWORD *)this + 6) = *((_DWORD *)this + 7);
  *((_DWORD *)this + 7) = a2;
  if ( a2 )
  {
    if ( !*((_DWORD *)this + 8) )
    {
      v3 = *((_DWORD *)this + 3);
      *((_DWORD *)this + 9) = GetTickCount() - v3;
      *((_DWORD *)this + 10) = *((_DWORD *)this + 7);
    }
    ++*((_DWORD *)this + 8);
  }
  Imapi2Utility::CTaskTimeEstimator::UpdateTime(this);
  if ( *((_DWORD *)this + 7) == *((_DWORD *)this + 5) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        126,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        *(unsigned int *)this,
        *((_DWORD *)this + 1));
    }
    *((_BYTE *)this + 17) = 1;
  }
}

```

## disassembly

```asm
0x180048d4c  mov     [rsp+arg_0], rbx
0x180048d51  push    rdi
0x180048d52  sub     rsp, 30h
0x180048d56  cmp     edx, [rcx+14h]
0x180048d59  mov     rdi, rcx
0x180048d5c  mov     eax, [rcx+1Ch]
0x180048d5f  cmovnb  edx, [rcx+14h]
0x180048d63  mov     [rcx+18h], eax
0x180048d66  mov     [rcx+1Ch], edx
0x180048d69  test    edx, edx
0x180048d6b  jz      short loc_180048D8A
0x180048d6d  cmp     dword ptr [rcx+20h], 0
0x180048d71  jnz     short loc_180048D87
0x180048d73  mov     ebx, [rcx+0Ch]
0x180048d76  call    cs:__imp_GetTickCount
0x180048d7c  sub     eax, ebx
0x180048d7e  mov     [rdi+24h], eax
0x180048d81  mov     eax, [rdi+1Ch]
0x180048d84  mov     [rdi+28h], eax
0x180048d87  inc     dword ptr [rdi+20h]
0x180048d8a  mov     rcx, rdi; this
0x180048d8d  call    ?UpdateTime@CTaskTimeEstimator@Imapi2Utility@@AEAAXXZ; Imapi2Utility::CTaskTimeEstimator::UpdateTime(void)
0x180048d92  mov     eax, [rdi+14h]
0x180048d95  cmp     [rdi+1Ch], eax
0x180048d98  jnz     short loc_180048DDC
0x180048d9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048da1  lea     rax, WPP_GLOBAL_Control
0x180048da8  cmp     rcx, rax
0x180048dab  jz      short loc_180048DD8
0x180048dad  test    byte ptr [rcx+1Ch], 4
0x180048db1  jz      short loc_180048DD8
0x180048db3  cmp     byte ptr [rcx+19h], 4
0x180048db7  jb      short loc_180048DD8
0x180048db9  mov     eax, [rdi+4]
0x180048dbc  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180048dc3  mov     r9d, [rdi]
0x180048dc6  mov     edx, 7Eh ; '~'
0x180048dcb  mov     rcx, [rcx+10h]
0x180048dcf  mov     [rsp+38h+var_18], eax
0x180048dd3  call    WPP_SF_Dd
0x180048dd8  mov     byte ptr [rdi+11h], 1
0x180048ddc  mov     rbx, [rsp+38h+arg_0]
0x180048de1  add     rsp, 30h
0x180048de5  pop     rdi
0x180048de6  retn
```
