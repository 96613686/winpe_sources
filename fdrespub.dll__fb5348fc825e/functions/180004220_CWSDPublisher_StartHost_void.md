# CWSDPublisher::StartHost(void)

- ea: `0x180004220`
- end: `0x180004340`
- name: `?StartHost@CWSDPublisher@@IEAAJXZ`
- size: `288`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800022b4`

## callees

- `0x180001f24`
- `0x180001f70`
- `0x180002dc4`
- `0x180003404`
- `0x18000356c`
- `0x180004220`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::StartHost(CWSDPublisher *this)
{
  _BYTE *v2; // rcx
  unsigned int StartValue; // ebx
  int v4; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rcx
  int v6; // eax
  bool v7; // cf
  char *v9; // [rsp+20h] [rbp-18h]
  __int64 Data; // [rsp+40h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v9 = (char *)this;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  StartValue = 0;
  if ( !*((_DWORD *)this + 7) )
  {
    Data = 0;
    StartValue = GetStartValue((BYTE *)&Data);
    if ( StartValue )
      goto LABEL_16;
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, char *))(**((_QWORD **)this + 9) + 32LL))(
           *((_QWORD *)this + 9),
           Data,
           0,
           0,
           v9);
    StartValue = v4;
    if ( v4 )
    {
      LogError(v5, v4, L"IWSDDeviceHost::Start", 1684);
    }
    else
    {
      *((_DWORD *)this + 5) = 1;
      LogEvent(&EventResume, L"BeginPublication");
    }
    *((_DWORD *)this + 6) = 0;
    if ( StartValue )
    {
LABEL_16:
      v2 = WPP_GLOBAL_Control;
      v6 = 0;
      v7 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
      goto LABEL_12;
    }
    v2 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  v7 = v2[25] < 4u;
LABEL_12:
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v6) = !v7;
    if ( v6 )
      WPP_SF_sqd(*((_QWORD *)v2 + 2), 34, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
  }
  return StartValue;
}

```

## disassembly

```asm
0x180004220  mov     [rsp+arg_8], rbx
0x180004225  mov     [rsp+arg_10], rbp
0x18000422a  push    rdi
0x18000422b  sub     rsp, 30h
0x18000422f  mov     rdi, rcx
0x180004232  mov     rcx, cs:WPP_GLOBAL_Control
0x180004239  lea     rbp, WPP_GLOBAL_Control
0x180004240  cmp     rcx, rbp
0x180004243  jz      short loc_18000426C
0x180004245  cmp     byte ptr [rcx+19h], 4
0x180004249  jb      short loc_18000426C
0x18000424b  mov     rcx, [rcx+10h]
0x18000424f  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180004256  mov     edx, 21h ; '!'
0x18000425b  mov     [rsp+38h+var_18], rdi; char *
0x180004260  call    WPP_SF_sq
0x180004265  mov     rcx, cs:WPP_GLOBAL_Control
0x18000426c  xor     ebx, ebx
0x18000426e  cmp     [rdi+1Ch], ebx
0x180004271  jnz     short loc_1800042EF
0x180004273  lea     rcx, [rsp+38h+Data]; lpData
0x180004278  mov     [rsp+38h+Data], rbx
0x18000427d  call    ?GetStartValue@@YAJPEA_K@Z; GetStartValue(unsigned __int64 *)
0x180004282  mov     ebx, eax
0x180004284  test    eax, eax
0x180004286  jnz     loc_180004331
0x18000428c  mov     rcx, [rdi+48h]
0x180004290  xor     r9d, r9d
0x180004293  mov     rdx, [rsp+38h+Data]
0x180004298  xor     r8d, r8d
0x18000429b  mov     rax, [rcx]
0x18000429e  mov     rax, [rax+20h]
0x1800042a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a7  mov     ebx, eax
0x1800042a9  test    eax, eax
0x1800042ab  jz      short loc_1800042C3
0x1800042ad  mov     r9d, 694h; unsigned int
0x1800042b3  lea     r8, aIwsddevicehost_0; "IWSDDeviceHost::Start"
0x1800042ba  mov     edx, eax; int
0x1800042bc  call    ?LogError@@YAJPEBU_EVENT_DESCRIPTOR@@JPEBGKPEBD@Z; LogError(_EVENT_DESCRIPTOR const *,long,ushort const *,ulong,char const *)
0x1800042c1  jmp     short loc_1800042DD
0x1800042c3  lea     rdx, aBeginpublicati; "BeginPublication"
0x1800042ca  mov     dword ptr [rdi+14h], 1
0x1800042d1  lea     rcx, EventResume; struct _EVENT_DESCRIPTOR *
0x1800042d8  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x1800042dd  mov     dword ptr [rdi+18h], 0
0x1800042e4  test    ebx, ebx
0x1800042e6  jnz     short loc_180004331
0x1800042e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042ef  xor     eax, eax
0x1800042f1  cmp     byte ptr [rcx+19h], 4
0x1800042f5  setnb   al
0x1800042f8  cmp     rcx, rbp
0x1800042fb  jz      short loc_18000431F
0x1800042fd  test    eax, eax
0x1800042ff  jz      short loc_18000431F
0x180004301  mov     rcx, [rcx+10h]
0x180004305  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x18000430c  mov     edx, 22h ; '"'
0x180004311  mov     [rsp+38h+var_10], ebx
0x180004315  mov     [rsp+38h+var_18], rdi
0x18000431a  call    WPP_SF_sqd
0x18000431f  mov     rbp, [rsp+38h+arg_10]
0x180004324  mov     eax, ebx
0x180004326  mov     rbx, [rsp+38h+arg_8]
0x18000432b  add     rsp, 30h
0x18000432f  pop     rdi
0x180004330  retn
0x180004331  mov     rcx, cs:WPP_GLOBAL_Control
0x180004338  xor     eax, eax
0x18000433a  cmp     byte ptr [rcx+19h], 2
0x18000433e  jmp     short loc_1800042F5
```
