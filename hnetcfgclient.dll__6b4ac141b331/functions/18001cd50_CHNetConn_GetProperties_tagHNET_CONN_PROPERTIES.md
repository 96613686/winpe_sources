# CHNetConn::GetProperties(tagHNET_CONN_PROPERTIES * *)

- ea: `0x18001cd50`
- end: `0x18001cf1b`
- name: `?GetProperties@CHNetConn@@UEAAJPEAPEAUtagHNET_CONN_PROPERTIES@@@Z`
- size: `459`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, struct tagHNET_CONN_PROPERTIES **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001b1e8`
- `0x18001cd50`
- `0x18001e130`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cdf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cecc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cecc`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetProperties(CHNetConn *this, struct tagHNET_CONN_PROPERTIES **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  struct tagHNET_CONN_PROPERTIES *v7; // rax
  int ConnectionPropertiesObject; // eax
  int Properties; // eax
  struct IWbemClassObject *v11; // [rsp+48h] [rbp+10h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = 0;
  if ( a2 )
  {
    v7 = (struct tagHNET_CONN_PROPERTIES *)CoTaskMemAlloc(0xCu);
    *a2 = v7;
    if ( v7 )
    {
      ConnectionPropertiesObject = CHNetConn::GetConnectionPropertiesObject(this, &v11);
      v5 = ConnectionPropertiesObject;
      if ( ConnectionPropertiesObject >= 0 )
      {
        if ( ConnectionPropertiesObject )
          goto LABEL_29;
        Properties = CHNetConn::InternalGetProperties(this, v11, *a2);
        v5 = Properties;
        if ( Properties < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)Properties);
        }
        ((void (__fastcall *)(struct IWbemClassObject *))v11->lpVtbl->Release)(v11);
        if ( (v5 & 0x80000000) == 0 )
          goto LABEL_29;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          72,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)ConnectionPropertiesObject);
      }
      CoTaskMemFree(*a2);
      *a2 = 0;
LABEL_29:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_30;
    }
    v5 = -2147024882;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v5;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_30;
    v6 = 71;
LABEL_10:
    WPP_SF_d(v4[2], v6, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
    goto LABEL_29;
  }
  v5 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v6 = 70;
    goto LABEL_10;
  }
LABEL_30:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 74, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18001cd50  mov     [rsp+arg_0], rbx
0x18001cd55  mov     [rsp+arg_10], rsi
0x18001cd5a  push    rdi
0x18001cd5b  push    r14
0x18001cd5d  push    r15
0x18001cd5f  sub     rsp, 20h
0x18001cd63  mov     rdi, rdx
0x18001cd66  mov     rsi, rcx
0x18001cd69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd70  lea     r14, WPP_GLOBAL_Control
0x18001cd77  lea     r15, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001cd7e  cmp     rcx, r14
0x18001cd81  jz      short loc_18001CDA7
0x18001cd83  test    byte ptr [rcx+1Ch], 8
0x18001cd87  jz      short loc_18001CDA7
0x18001cd89  cmp     byte ptr [rcx+19h], 6
0x18001cd8d  jb      short loc_18001CDA7
0x18001cd8f  mov     rcx, [rcx+10h]
0x18001cd93  mov     edx, 45h ; 'E'
0x18001cd98  mov     r8, r15
0x18001cd9b  call    WPP_SF_
0x18001cda0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cda7  mov     [rsp+38h+arg_8], 0
0x18001cdb0  test    rdi, rdi
0x18001cdb3  jnz     short loc_18001CDEE
0x18001cdb5  mov     ebx, 80004003h
0x18001cdba  cmp     rcx, r14
0x18001cdbd  jz      loc_18001CF05
0x18001cdc3  test    byte ptr [rcx+1Ch], 8
0x18001cdc7  jz      loc_18001CEE0
0x18001cdcd  cmp     byte ptr [rcx+19h], 2
0x18001cdd1  jb      loc_18001CEE0
0x18001cdd7  lea     edx, [rdi+46h]
0x18001cdda  mov     rcx, [rcx+10h]
0x18001cdde  mov     r9d, ebx
0x18001cde1  mov     r8, r15
0x18001cde4  call    WPP_SF_d
0x18001cde9  jmp     loc_18001CED9
0x18001cdee  mov     ecx, 0Ch; cb
0x18001cdf3  call    cs:__imp_CoTaskMemAlloc
0x18001cdf9  mov     [rdi], rax
0x18001cdfc  test    rax, rax
0x18001cdff  jnz     short loc_18001CE2F
0x18001ce01  mov     ebx, 8007000Eh
0x18001ce06  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce0d  cmp     rcx, r14
0x18001ce10  jz      loc_18001CF05
0x18001ce16  test    byte ptr [rcx+1Ch], 8
0x18001ce1a  jz      loc_18001CEE0
0x18001ce20  cmp     byte ptr [rcx+19h], 2
0x18001ce24  jb      loc_18001CEE0
0x18001ce2a  lea     edx, [rax+47h]
0x18001ce2d  jmp     short loc_18001CDDA
0x18001ce2f  lea     rdx, [rsp+38h+arg_8]; struct IWbemClassObject **
0x18001ce34  mov     rcx, rsi; this
0x18001ce37  call    ?GetConnectionPropertiesObject@CHNetConn@@IEAAJPEAPEAUIWbemClassObject@@@Z; CHNetConn::GetConnectionPropertiesObject(IWbemClassObject * *)
0x18001ce3c  mov     ebx, eax
0x18001ce3e  test    eax, eax
0x18001ce40  jns     short loc_18001CE70
0x18001ce42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce49  cmp     rcx, r14
0x18001ce4c  jz      short loc_18001CEC9
0x18001ce4e  test    byte ptr [rcx+1Ch], 8
0x18001ce52  jz      short loc_18001CEC9
0x18001ce54  cmp     byte ptr [rcx+19h], 2
0x18001ce58  jb      short loc_18001CEC9
0x18001ce5a  mov     rcx, [rcx+10h]
0x18001ce5e  mov     edx, 48h ; 'H'
0x18001ce63  mov     r9d, eax
0x18001ce66  mov     r8, r15
0x18001ce69  call    WPP_SF_d
0x18001ce6e  jmp     short loc_18001CEC9
0x18001ce70  jnz     short loc_18001CED9
0x18001ce72  mov     r8, [rdi]; struct tagHNET_CONN_PROPERTIES *
0x18001ce75  mov     rcx, rsi; this
0x18001ce78  mov     rdx, [rsp+38h+arg_8]; struct IWbemClassObject *
0x18001ce7d  call    ?InternalGetProperties@CHNetConn@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_CONN_PROPERTIES@@@Z; CHNetConn::InternalGetProperties(IWbemClassObject *,tagHNET_CONN_PROPERTIES *)
0x18001ce82  mov     ebx, eax
0x18001ce84  test    eax, eax
0x18001ce86  jns     short loc_18001CEB4
0x18001ce88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce8f  cmp     rcx, r14
0x18001ce92  jz      short loc_18001CEB4
0x18001ce94  test    byte ptr [rcx+1Ch], 8
0x18001ce98  jz      short loc_18001CEB4
0x18001ce9a  cmp     byte ptr [rcx+19h], 2
0x18001ce9e  jb      short loc_18001CEB4
0x18001cea0  mov     rcx, [rcx+10h]
0x18001cea4  mov     edx, 49h ; 'I'
0x18001cea9  mov     r9d, eax
0x18001ceac  mov     r8, r15
0x18001ceaf  call    WPP_SF_d
0x18001ceb4  mov     rcx, [rsp+38h+arg_8]
0x18001ceb9  mov     rax, [rcx]
0x18001cebc  mov     rax, [rax+10h]
0x18001cec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec5  test    ebx, ebx
0x18001cec7  jns     short loc_18001CED9
0x18001cec9  mov     rcx, [rdi]; pv
0x18001cecc  call    cs:__imp_CoTaskMemFree
0x18001ced2  mov     qword ptr [rdi], 0
0x18001ced9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cee0  cmp     rcx, r14
0x18001cee3  jz      short loc_18001CF05
0x18001cee5  test    byte ptr [rcx+1Ch], 8
0x18001cee9  jz      short loc_18001CF05
0x18001ceeb  cmp     byte ptr [rcx+19h], 6
0x18001ceef  jb      short loc_18001CF05
0x18001cef1  mov     rcx, [rcx+10h]
0x18001cef5  mov     edx, 4Ah ; 'J'
0x18001cefa  mov     r9d, ebx
0x18001cefd  mov     r8, r15
0x18001cf00  call    WPP_SF_d
0x18001cf05  mov     rsi, [rsp+38h+arg_10]
0x18001cf0a  mov     eax, ebx
0x18001cf0c  mov     rbx, [rsp+38h+arg_0]
0x18001cf11  add     rsp, 20h
0x18001cf15  pop     r15
0x18001cf17  pop     r14
0x18001cf19  pop     rdi
0x18001cf1a  retn
```
