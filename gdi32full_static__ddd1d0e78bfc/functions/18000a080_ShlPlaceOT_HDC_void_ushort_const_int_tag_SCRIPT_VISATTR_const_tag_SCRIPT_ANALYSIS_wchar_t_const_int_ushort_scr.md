# ShlPlaceOT(HDC__ *,void * *,ushort const *,int,tag_SCRIPT_VISATTR const *,tag_SCRIPT_ANALYSIS *,wchar_t const *,int,ushort *,script_charprop *,ulong,ulong,int *,textrange_properties * *,int,int *,tagGOFFSET *,_ABC *)

- ea: `0x18000a080`
- end: `0x18000a8f6`
- name: `?ShlPlaceOT@@YAJPEAUHDC__@@PEAPEAXPEBGHPEBUtag_SCRIPT_VISATTR@@PEAUtag_SCRIPT_ANALYSIS@@PEB_WHPEAGPEAUscript_charprop@@KKPEAHPEAPEAUtextrange_properties@@H8PEAUtagGOFFSET@@PEAU_ABC@@@Z`
- size: `2166`
- prototype: `__int64 __fastcall(HDC, void **, const unsigned __int16 *, int, const struct tag_SCRIPT_VISATTR *, struct tag_SCRIPT_ANALYSIS *, const wchar_t *, int, unsigned __int16 *, struct script_charprop *, unsigned int, unsigned int, int *, struct textrange_properties **, int, int *, struct tagGOFFSET *, struct _ABC *)`
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180009460`
- `0x180009900`
- `0x18000a990`
- `0x18001b2d0`
- `0x180026720`

## callees

- `0x180004bc0`
- `0x18000512c`
- `0x1800051ac`
- `0x18000a080`
- `0x18000d040`
- `0x18001a384`
- `0x18001ba90`
- `0x1800377b0`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a67d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a67d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a651`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a651`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a6a8`
- `TextShaping!ShapingGetGlyphPositions` at `0x18000a2c6`
- `TextShaping!ShapingGetGlyphPositions` at `0x18000a2c6`

## string_xrefs

- `0x18000a195`: `dfltlatnlatnlatnlatnlatnlatngrekcyrlarmngeorlatndfltDFLTkanakanakanahanihanghangbopoyi  hanidflthebrhebrarabarabarabarabsyrcthaithaithaidev2dev2tml2tml2bng2bng2bng2gur2gur2gjr2gjr2gjr2ory2ory2tel2tel2knd2knd2mlm2mlm2tibttibtlao lao khmrkhmrmym2mymrmongmongethiethithaacanscherbrairunrogamsinhlatndflttaletalutaluphagnko dsrtmathosmaosmatfngvai vai lisulatnglagitalgothorkhqavsbugijavacoptolckolcksoratglghanobuhdtagblimblimbbalibalisundsundlepclepcsylosaursaurkalikalirjngchamchamlinblycicariugarxpeo`

## pseudocode

```c

```
