# MkvMfSourceLib::InitializeTagMaps

- ea: `0x1800296f8`
- end: `0x18002a85e`
- name: `MkvMfSourceLib::InitializeTagMaps`
- size: `4454`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a864`

## callees

- `0x1800023e0`
- `0x180008a74`
- `0x18000a968`
- `0x18002877c`
- `0x180028e7c`
- `0x180028f44`
- `0x1800296f8`

## string_xrefs

- `0x180029790`: `ACCOMPANIMENT`
- `0x1800297c5`: `COMPOSER`
- `0x18002a2cb`: `COMPOSITION_LOCATION`
- `0x18002a335`: `COMMENT`
- `0x18002a300`: `COMPOSER_NATIONALITY`
- `0x18002a602`: `PRODUCTION_COPYRIGHT`
- `0x18002a5c6`: `COPYRIGHT`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 MkvMfSourceLib::InitializeTagMaps()
{
  const char *v0; // r9
  __int64 result; // rax
  _BYTE v2[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v3[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    std::wstring::wstring(v3, L"ARTIST");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Artist;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LEAD_PERFORMER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ACCOMPANIMENT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Composer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ARRANGER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LYRICS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Lyrics;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LYRICIST");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CONDUCTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Conductor;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Video_Director;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ASSISTANT_DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DIRECTOR_OF_PHOTOGRAPHY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SOUND_ENGINEER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ART_DIRECTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_DESIGNER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CHOREGRAPHER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COSTUME_DESIGNER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ACTOR");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CHARACTER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"WRITTEN_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Writer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SCREENPLAY_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"EDITED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Producer;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COPRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"EXECUTIVE_PRODUCER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DISTRIBUTED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MASTERED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_EncodedBy;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MIXED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REMIXED_BY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_STUDIO");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"THANKS_TO");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PUBLISHER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_Publisher;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LABEL");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"GENRE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Genre;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MOOD");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Mood;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ORIGINAL_MEDIA_TYPE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"CONTENT_TYPE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUBJECT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DESCRIPTION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Comment;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"KEYWORDS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Keywords;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUMMARY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SYNOPSIS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"INITIAL_KEY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_InitialKey;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PERIOD");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_Period;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LAW_RATING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_ParentalRating;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ICRA");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_RELEASED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_DateReleased;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_RECORDED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_ENCODED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_DateEncoded;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_TAGGED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_DIGITIZED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_WRITTEN");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"DATE_PURCHASED");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"RECORDING_LOCATION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSITION_LOCATION");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMPOSER_NATIONALITY");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COMMENT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Comment;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PLAY_COUNTER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"RATING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Rating;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODER");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ENCODER_SETTINGS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_EncodingSettings;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"BPS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"FPS");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"BPM");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Music_BeatsPerMinute;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"MEASURE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TUNING");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REPLAYGAIN_GAIN");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"REPLAYGAIN_PEAK");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"COPYRIGHT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Copyright;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PRODUCTION_COPYRIGHT");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"LICENSE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TERMS_OF_USE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = 0;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TITLE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Title;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"SUBTITLE");
    *(_QWORD *)(*(_QWORD *)std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(
                             &qword_1800D6EC0,
                             v2,
                             v3)
              + 64LL) = &PKEY_Media_SubTitle;
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"TITLE");
    MkvMfSourceLib::AddAudioTag(50, v3, &PKEY_Music_AlbumTitle);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"ARTIST");
    MkvMfSourceLib::AddAudioTag(50, v3, &PKEY_Music_AlbumArtist);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddAudioTag(30, v3, &PKEY_Music_TrackNumber);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddAudioTag(40, v3, &PKEY_Music_PartOfSet);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddVideoTag(60, v3, &PKEY_Media_SeasonNumber);
    std::wstring::_Tidy_deallocate(v3);
    std::wstring::wstring(v3, L"PART_NUMBER");
    MkvMfSourceLib::AddVideoTag(50, v3, &PKEY_Media_EpisodeNumber);
    std::wstring::_Tidy_deallocate(v3);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16C,
                           (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmetadata.cpp",
                           v0);
  }
  return result;
}

```

## disassembly

```asm
0x1800296f8  mov     [rsp+arg_0], rbx
0x1800296fd  mov     [rsp+arg_8], rsi
0x180029702  push    rdi
0x180029703  sub     rsp, 60h
0x180029707  mov     rax, cs:__security_cookie
0x18002970e  xor     rax, rsp
0x180029711  mov     [rsp+68h+var_10], rax
0x180029716  lea     rdx, aArtist; "ARTIST"
0x18002971d  lea     rcx, [rsp+68h+var_30]
0x180029722  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029727  nop
0x180029728  lea     r8, [rsp+68h+var_30]
0x18002972d  lea     rdx, [rsp+68h+var_48]
0x180029732  lea     rbx, qword_1800D6EC0
0x180029739  mov     rcx, rbx
0x18002973c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029741  mov     rax, [rax]
0x180029744  lea     rcx, PKEY_Music_Artist
0x18002974b  mov     [rax+40h], rcx
0x18002974f  lea     rcx, [rsp+68h+var_30]
0x180029754  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029759  lea     rdx, aLeadPerformer; "LEAD_PERFORMER"
0x180029760  lea     rcx, [rsp+68h+var_30]
0x180029765  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002976a  nop
0x18002976b  lea     r8, [rsp+68h+var_30]
0x180029770  lea     rdx, [rsp+68h+var_48]
0x180029775  mov     rcx, rbx
0x180029778  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002977d  mov     rax, [rax]
0x180029780  xor     edi, edi
0x180029782  mov     [rax+40h], rdi
0x180029786  lea     rcx, [rsp+68h+var_30]
0x18002978b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029790  lea     rdx, aAccompaniment; "ACCOMPANIMENT"
0x180029797  lea     rcx, [rsp+68h+var_30]
0x18002979c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800297a1  nop
0x1800297a2  lea     r8, [rsp+68h+var_30]
0x1800297a7  lea     rdx, [rsp+68h+var_48]
0x1800297ac  mov     rcx, rbx
0x1800297af  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800297b4  mov     rax, [rax]
0x1800297b7  mov     [rax+40h], rdi
0x1800297bb  lea     rcx, [rsp+68h+var_30]
0x1800297c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800297c5  lea     rdx, aComposer; "COMPOSER"
0x1800297cc  lea     rcx, [rsp+68h+var_30]
0x1800297d1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800297d6  nop
0x1800297d7  lea     r8, [rsp+68h+var_30]
0x1800297dc  lea     rdx, [rsp+68h+var_48]
0x1800297e1  mov     rcx, rbx
0x1800297e4  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800297e9  mov     rax, [rax]
0x1800297ec  lea     rcx, PKEY_Music_Composer
0x1800297f3  mov     [rax+40h], rcx
0x1800297f7  lea     rcx, [rsp+68h+var_30]
0x1800297fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029801  lea     rdx, aArranger; "ARRANGER"
0x180029808  lea     rcx, [rsp+68h+var_30]
0x18002980d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029812  nop
0x180029813  lea     r8, [rsp+68h+var_30]
0x180029818  lea     rdx, [rsp+68h+var_48]
0x18002981d  mov     rcx, rbx
0x180029820  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029825  mov     rax, [rax]
0x180029828  mov     [rax+40h], rdi
0x18002982c  lea     rcx, [rsp+68h+var_30]
0x180029831  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029836  lea     rdx, aLyrics; "LYRICS"
0x18002983d  lea     rcx, [rsp+68h+var_30]
0x180029842  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029847  nop
0x180029848  lea     r8, [rsp+68h+var_30]
0x18002984d  lea     rdx, [rsp+68h+var_48]
0x180029852  mov     rcx, rbx
0x180029855  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18002985a  mov     rax, [rax]
0x18002985d  lea     rcx, PKEY_Music_Lyrics
0x180029864  mov     [rax+40h], rcx
0x180029868  lea     rcx, [rsp+68h+var_30]
0x18002986d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029872  lea     rdx, aLyricist; "LYRICIST"
0x180029879  lea     rcx, [rsp+68h+var_30]
0x18002987e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029883  nop
0x180029884  lea     r8, [rsp+68h+var_30]
0x180029889  lea     rdx, [rsp+68h+var_48]
0x18002988e  mov     rcx, rbx
0x180029891  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029896  mov     rax, [rax]
0x180029899  mov     [rax+40h], rdi
0x18002989d  lea     rcx, [rsp+68h+var_30]
0x1800298a2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298a7  lea     rdx, aConductor; "CONDUCTOR"
0x1800298ae  lea     rcx, [rsp+68h+var_30]
0x1800298b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800298b8  nop
0x1800298b9  lea     r8, [rsp+68h+var_30]
0x1800298be  lea     rdx, [rsp+68h+var_48]
0x1800298c3  mov     rcx, rbx
0x1800298c6  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800298cb  mov     rax, [rax]
0x1800298ce  lea     rcx, PKEY_Music_Conductor
0x1800298d5  mov     [rax+40h], rcx
0x1800298d9  lea     rcx, [rsp+68h+var_30]
0x1800298de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800298e3  lea     rdx, aDirector; "DIRECTOR"
0x1800298ea  lea     rcx, [rsp+68h+var_30]
0x1800298ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800298f4  nop
0x1800298f5  lea     r8, [rsp+68h+var_30]
0x1800298fa  lea     rdx, [rsp+68h+var_48]
0x1800298ff  mov     rcx, rbx
0x180029902  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029907  mov     rax, [rax]
0x18002990a  lea     rcx, PKEY_Video_Director
0x180029911  mov     [rax+40h], rcx
0x180029915  lea     rcx, [rsp+68h+var_30]
0x18002991a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002991f  lea     rdx, aAssistantDirec; "ASSISTANT_DIRECTOR"
0x180029926  lea     rcx, [rsp+68h+var_30]
0x18002992b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029930  nop
0x180029931  lea     r8, [rsp+68h+var_30]
0x180029936  lea     rdx, [rsp+68h+var_48]
0x18002993b  mov     rcx, rbx
0x18002993e  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029943  mov     rax, [rax]
0x180029946  mov     [rax+40h], rdi
0x18002994a  lea     rcx, [rsp+68h+var_30]
0x18002994f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029954  lea     rdx, aDirectorOfPhot; "DIRECTOR_OF_PHOTOGRAPHY"
0x18002995b  lea     rcx, [rsp+68h+var_30]
0x180029960  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029965  nop
0x180029966  lea     r8, [rsp+68h+var_30]
0x18002996b  lea     rdx, [rsp+68h+var_48]
0x180029970  mov     rcx, rbx
0x180029973  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029978  mov     rax, [rax]
0x18002997b  mov     [rax+40h], rdi
0x18002997f  lea     rcx, [rsp+68h+var_30]
0x180029984  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029989  lea     rdx, aSoundEngineer; "SOUND_ENGINEER"
0x180029990  lea     rcx, [rsp+68h+var_30]
0x180029995  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002999a  nop
0x18002999b  lea     r8, [rsp+68h+var_30]
0x1800299a0  lea     rdx, [rsp+68h+var_48]
0x1800299a5  mov     rcx, rbx
0x1800299a8  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800299ad  mov     rax, [rax]
0x1800299b0  mov     [rax+40h], rdi
0x1800299b4  lea     rcx, [rsp+68h+var_30]
0x1800299b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800299be  lea     rdx, aArtDirector; "ART_DIRECTOR"
0x1800299c5  lea     rcx, [rsp+68h+var_30]
0x1800299ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800299cf  nop
0x1800299d0  lea     r8, [rsp+68h+var_30]
0x1800299d5  lea     rdx, [rsp+68h+var_48]
0x1800299da  mov     rcx, rbx
0x1800299dd  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800299e2  mov     rax, [rax]
0x1800299e5  mov     [rax+40h], rdi
0x1800299e9  lea     rcx, [rsp+68h+var_30]
0x1800299ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800299f3  lea     rdx, aProductionDesi; "PRODUCTION_DESIGNER"
0x1800299fa  lea     rcx, [rsp+68h+var_30]
0x1800299ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029a04  nop
0x180029a05  lea     r8, [rsp+68h+var_30]
0x180029a0a  lea     rdx, [rsp+68h+var_48]
0x180029a0f  mov     rcx, rbx
0x180029a12  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029a17  mov     rax, [rax]
0x180029a1a  mov     [rax+40h], rdi
0x180029a1e  lea     rcx, [rsp+68h+var_30]
0x180029a23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a28  lea     rdx, aChoregrapher; "CHOREGRAPHER"
0x180029a2f  lea     rcx, [rsp+68h+var_30]
0x180029a34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029a39  nop
0x180029a3a  lea     r8, [rsp+68h+var_30]
0x180029a3f  lea     rdx, [rsp+68h+var_48]
0x180029a44  mov     rcx, rbx
0x180029a47  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029a4c  mov     rax, [rax]
0x180029a4f  mov     [rax+40h], rdi
0x180029a53  lea     rcx, [rsp+68h+var_30]
0x180029a58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a5d  lea     rdx, aCostumeDesigne; "COSTUME_DESIGNER"
0x180029a64  lea     rcx, [rsp+68h+var_30]
0x180029a69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029a6e  nop
0x180029a6f  lea     r8, [rsp+68h+var_30]
0x180029a74  lea     rdx, [rsp+68h+var_48]
0x180029a79  mov     rcx, rbx
0x180029a7c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029a81  mov     rax, [rax]
0x180029a84  mov     [rax+40h], rdi
0x180029a88  lea     rcx, [rsp+68h+var_30]
0x180029a8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a92  lea     rdx, aActor; "ACTOR"
0x180029a99  lea     rcx, [rsp+68h+var_30]
0x180029a9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029aa3  nop
0x180029aa4  lea     r8, [rsp+68h+var_30]
0x180029aa9  lea     rdx, [rsp+68h+var_48]
0x180029aae  mov     rcx, rbx
0x180029ab1  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029ab6  mov     rax, [rax]
0x180029ab9  mov     [rax+40h], rdi
0x180029abd  lea     rcx, [rsp+68h+var_30]
0x180029ac2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029ac7  lea     rdx, aCharacter; "CHARACTER"
0x180029ace  lea     rcx, [rsp+68h+var_30]
0x180029ad3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029ad8  nop
0x180029ad9  lea     r8, [rsp+68h+var_30]
0x180029ade  lea     rdx, [rsp+68h+var_48]
0x180029ae3  mov     rcx, rbx
0x180029ae6  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029aeb  mov     rax, [rax]
0x180029aee  mov     [rax+40h], rdi
0x180029af2  lea     rcx, [rsp+68h+var_30]
0x180029af7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029afc  lea     rdx, aWrittenBy; "WRITTEN_BY"
0x180029b03  lea     rcx, [rsp+68h+var_30]
0x180029b08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b0d  nop
0x180029b0e  lea     r8, [rsp+68h+var_30]
0x180029b13  lea     rdx, [rsp+68h+var_48]
0x180029b18  mov     rcx, rbx
0x180029b1b  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029b20  mov     rax, [rax]
0x180029b23  lea     rcx, PKEY_Media_Writer
0x180029b2a  mov     [rax+40h], rcx
0x180029b2e  lea     rcx, [rsp+68h+var_30]
0x180029b33  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029b38  lea     rdx, aScreenplayBy; "SCREENPLAY_BY"
0x180029b3f  lea     rcx, [rsp+68h+var_30]
0x180029b44  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b49  nop
0x180029b4a  lea     r8, [rsp+68h+var_30]
0x180029b4f  lea     rdx, [rsp+68h+var_48]
0x180029b54  mov     rcx, rbx
0x180029b57  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029b5c  mov     rax, [rax]
0x180029b5f  mov     [rax+40h], rdi
0x180029b63  lea     rcx, [rsp+68h+var_30]
0x180029b68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029b6d  lea     rdx, aEditedBy; "EDITED_BY"
0x180029b74  lea     rcx, [rsp+68h+var_30]
0x180029b79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b7e  nop
0x180029b7f  lea     r8, [rsp+68h+var_30]
0x180029b84  lea     rdx, [rsp+68h+var_48]
0x180029b89  mov     rcx, rbx
0x180029b8c  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029b91  mov     rax, [rax]
0x180029b94  mov     [rax+40h], rdi
0x180029b98  lea     rcx, [rsp+68h+var_30]
0x180029b9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029ba2  lea     rdx, aProducer; "PRODUCER"
0x180029ba9  lea     rcx, [rsp+68h+var_30]
0x180029bae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029bb3  nop
0x180029bb4  lea     r8, [rsp+68h+var_30]
0x180029bb9  lea     rdx, [rsp+68h+var_48]
0x180029bbe  mov     rcx, rbx
0x180029bc1  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029bc6  mov     rax, [rax]
0x180029bc9  lea     rcx, PKEY_Media_Producer
0x180029bd0  mov     [rax+40h], rcx
0x180029bd4  lea     rcx, [rsp+68h+var_30]
0x180029bd9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029bde  lea     rdx, aCoproducer; "COPRODUCER"
0x180029be5  lea     rcx, [rsp+68h+var_30]
0x180029bea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029bef  nop
0x180029bf0  lea     r8, [rsp+68h+var_30]
0x180029bf5  lea     rdx, [rsp+68h+var_48]
0x180029bfa  mov     rcx, rbx
0x180029bfd  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029c02  mov     rax, [rax]
0x180029c05  mov     [rax+40h], rdi
0x180029c09  lea     rcx, [rsp+68h+var_30]
0x180029c0e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029c13  lea     rdx, aExecutiveProdu; "EXECUTIVE_PRODUCER"
0x180029c1a  lea     rcx, [rsp+68h+var_30]
0x180029c1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029c24  nop
0x180029c25  lea     r8, [rsp+68h+var_30]
0x180029c2a  lea     rdx, [rsp+68h+var_48]
0x180029c2f  mov     rcx, rbx
0x180029c32  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_tagpropertykey@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,_tagpropertykey const *>::_Try_emplace<std::wstring const &,>(std::wstring const &)
  ... truncated ...
```
