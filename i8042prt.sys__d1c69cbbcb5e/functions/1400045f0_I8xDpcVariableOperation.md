# I8xDpcVariableOperation

- ea: `0x1400045f0`
- end: `0x14000476d`
- name: `I8xDpcVariableOperation`
- size: `381`
- prototype: `KSYNCHRONIZE_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004530`
- `0x1400045f0`
- `0x140004780`
- `0x140007b10`

## string_xrefs

- `0x14000471d`: `write`

## pseudocode

```c
BOOLEAN __fastcall I8xDpcVariableOperation(_DWORD *SynchronizeContext, int a2)
{
  int v3; // ecx
  int v4; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  const char *v9; // rdx
  int v10; // [rsp+20h] [rbp-28h]
  __int64 v11; // [rsp+28h] [rbp-20h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      7,
      75,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = SynchronizeContext[2];
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          v9 = "decrement";
        }
        else if ( v8 == 2 )
        {
          v9 = "write";
        }
        else
        {
          v9 = "read";
          if ( v8 != 3 )
            v9 = File;
        }
      }
      else
      {
        v9 = "increment";
      }
      WPP_RECORDER_SF_sqD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        v6,
        v7,
        v10,
        (__int64)v9,
        *(_QWORD *)SynchronizeContext,
        **(_DWORD **)SynchronizeContext);
    }
  }
  v3 = SynchronizeContext[2];
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LODWORD(v11) = **((_DWORD **)SynchronizeContext + 2);
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            8,
            77,
            (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
            v11);
        }
        **(_DWORD **)SynchronizeContext = **((_DWORD **)SynchronizeContext + 2);
      }
    }
    else
    {
      --**(_DWORD **)SynchronizeContext;
    }
  }
  else
  {
    ++**(_DWORD **)SynchronizeContext;
  }
  **((_DWORD **)SynchronizeContext + 2) = **(_DWORD **)SynchronizeContext;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v11) = **((_DWORD **)SynchronizeContext + 2);
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      7,
      78,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids,
      v11);
  }
  return 1;
}

```

## disassembly

```asm
0x1400045f0  mov     [rsp+arg_0], rbx
0x1400045f5  mov     [rsp+arg_8], rsi
0x1400045fa  push    rdi
0x1400045fb  sub     rsp, 40h
0x1400045ff  mov     rbx, rcx
0x140004602  lea     rdi, WPP_RECORDER_INITIALIZED
0x140004609  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140004610  lea     rsi, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140004617  jnz     loc_1400046A6
0x14000461d  mov     ecx, [rbx+8]
0x140004620  test    ecx, ecx
0x140004622  jz      short loc_140004630
0x140004624  sub     ecx, 1
0x140004627  jnz     short loc_140004660
0x140004629  mov     rax, [rbx]
0x14000462c  dec     dword ptr [rax]
0x14000462e  jmp     short loc_140004635
0x140004630  mov     rax, [rbx]
0x140004633  inc     dword ptr [rax]
0x140004635  mov     rax, [rbx]
0x140004638  mov     rcx, [rbx+10h]
0x14000463c  mov     eax, [rax]
0x14000463e  mov     [rcx], eax
0x140004640  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140004647  jnz     loc_14000473D
0x14000464d  mov     rbx, [rsp+48h+arg_0]
0x140004652  mov     al, 1
0x140004654  mov     rsi, [rsp+48h+arg_8]
0x140004659  add     rsp, 40h
0x14000465d  pop     rdi
0x14000465e  retn
0x140004660  cmp     ecx, 1
0x140004663  jnz     short loc_140004635
0x140004665  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000466c  jz      short loc_140004699
0x14000466e  mov     rax, [rbx+10h]
0x140004672  mov     r9d, 4Dh ; 'M'
0x140004678  mov     rcx, cs:WPP_GLOBAL_Control
0x14000467f  mov     r8d, 8
0x140004685  mov     eax, [rax]
0x140004687  mov     rcx, [rcx+40h]
0x14000468b  mov     dword ptr [rsp+48h+var_20], eax
0x14000468f  mov     [rsp+48h+var_28], rsi
0x140004694  call    WPP_RECORDER_SF_D
0x140004699  mov     rax, [rbx+10h]
0x14000469d  mov     rcx, [rbx]
0x1400046a0  mov     eax, [rax]
0x1400046a2  mov     [rcx], eax
0x1400046a4  jmp     short loc_140004635
0x1400046a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046ad  mov     r9d, 4Bh ; 'K'
0x1400046b3  mov     r8d, 7
0x1400046b9  mov     [rsp+48h+var_28], rsi
0x1400046be  mov     rcx, [rcx+40h]
0x1400046c2  call    WPP_RECORDER_SF_
0x1400046c7  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400046ce  jz      loc_14000461D
0x1400046d4  mov     eax, [rbx+8]
0x1400046d7  test    eax, eax
0x1400046d9  jnz     short loc_14000470A
0x1400046db  lea     rdx, aIncrement; "increment"
0x1400046e2  mov     rcx, [rbx]
0x1400046e5  mov     eax, [rcx]
0x1400046e7  mov     [rsp+48h+var_10], eax
0x1400046eb  mov     [rsp+48h+var_18], rcx
0x1400046f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046f7  mov     [rsp+48h+var_20], rdx
0x1400046fc  mov     rcx, [rcx+40h]
0x140004700  call    WPP_RECORDER_SF_sqD
0x140004705  jmp     loc_14000461D
0x14000470a  cmp     eax, 1
0x14000470d  jnz     short loc_140004718
0x14000470f  lea     rdx, aDecrement; "decrement"
0x140004716  jmp     short loc_1400046E2
0x140004718  cmp     eax, 2
0x14000471b  jnz     short loc_140004726
0x14000471d  lea     rdx, aWrite; "write"
0x140004724  jmp     short loc_1400046E2
0x140004726  cmp     eax, 3
0x140004729  lea     rdx, aRead; "read"
0x140004730  lea     rcx, File
0x140004737  cmovnz  rdx, rcx
0x14000473b  jmp     short loc_1400046E2
0x14000473d  mov     rax, [rbx+10h]
0x140004741  mov     r9d, 4Eh ; 'N'
0x140004747  mov     rcx, cs:WPP_GLOBAL_Control
0x14000474e  mov     r8d, 7
0x140004754  mov     eax, [rax]
0x140004756  mov     rcx, [rcx+40h]
0x14000475a  mov     dword ptr [rsp+48h+var_20], eax
0x14000475e  mov     [rsp+48h+var_28], rsi
0x140004763  call    WPP_RECORDER_SF_D
0x140004768  jmp     loc_14000464D
```
